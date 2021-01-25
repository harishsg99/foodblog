---
layout: blog
title: Create your own Newsletter with Next.js API Routes and Mailchimp
date: 2021-01-25T07:38:50.894Z
---
<!--StartFragment-->

## Setting up Mailchimp

After [creating an account](https://mailchimp.com/help/create-an-account/), you'll need to fetch your [API key](https://mailchimp.com/help/about-api-keys/#find+or+generate+your+api+key). You can utilize their [API Playground](https://us1.api.mailchimp.com/playground/?_ga=2.231663199.1180055433.1567349670-195619933.1565803046) to test requests.

When a user clicks "subscribe", we'll want to add their email address to the mailing list. This is through the [List Members POST](https://developer.mailchimp.com/documentation/mailchimp/reference/lists/members/#create-post_lists_list_id_members) endpoint.

According to their [API documentation](https://developer.mailchimp.com/documentation/mailchimp/guides/get-started-with-mailchimp-api-3/), we'll need to send a request to:

```bash
https://<dc>.api.mailchimp.com/3.0
```

Where `dc` is the datacenter. This is the last 3 characters of your API key we retrieved earlier. We'll also need to fetch the [Audience ID](https://mailchimp.com/help/find-audience-id/) (or List ID) for the mailing list.

## Environment Variables

Let's make our secrets we've retrieved available without hardcoding them into our request. Since I'm deploying with [Vercel](https://vercel.com/), I'll need to set up some [environment variables](https://nextjs.org/docs/basic-features/environment-variables). First, let's create `.env.local` for testing locally.

.env.local

```bash
MAILCHIMP_LIST_ID=<secret-value>
MAILCHIMP_API_KEY=<secret-value>
```

Finally, [add these environment variables in Vercel](https://vercel.com/docs/environment-variables) so they're available on pull requests (Preview) and in Production.

**Note:** Don't forget to add `.env.local` to your `.gitignore`. We don't want to commit our secrets.

## Creating The Request

Now that we have the API Key and the List ID available as environment variables, we can create an API route at `pages/api/subscribe.js` to add a member to our list.

pages/api/subscribe.js

```js
export default async (req, res) => {

  const { email } = req.body;

  if (!email) {
    return res.status(400).json({ error: 'Email is required' });
  }

  try {
    const LIST_ID = process.env.MAILCHIMP_LIST_ID;
    const API_KEY = process.env.MAILCHIMP_API_KEY;
    const DATACENTER = API_KEY.split('-')[1];

    const data = {
      email_address: email,
      status: 'subscribed'
    };


    const response = await fetch(
      `https://${DATACENTER}.api.mailchimp.com/3.0/lists/${LIST_ID}/members`,
      {
        body: JSON.stringify(data),
        headers: {
          Authorization: `apikey ${API_KEY}`,
          'Content-Type': 'application/json'
        },
        method: 'POST'
      }
    );

    if (response.status >= 400) {
      return res.status(400).json({
        error: `There was an error subscribing to the newsletter. Shoot me an email at [me@leerob.io] and I'll add you to the list.`
      });
    }

    return res.status(201).json({ error: '' });
  } catch (error) {
    return res.status(500).json({ error: error.message || error.toString() });
  }
};
```

## Creating A Form Input

Now that our API is created, we need a way to gather user input. Let's create a component to send a request to our API.

components/Subscribe.js

```js
import React, { useRef, useState } from 'react';

function Subscribe() {
  const inputEl = useRef(null);
  const [message, setMessage] = useState('');

  const subscribe = async (e) => {
    e.preventDefault();

    const res = await fetch('/api/subscribe', {
      body: JSON.stringify({
        email: inputEl.current.value
      }),
      headers: {
        'Content-Type': 'application/json'
      },
      method: 'POST'
    });

    const { error } = await res.json();

    if (error) {
     
      setMessage(error);

      return;
    }

    inputEl.current.value = '';
    setMessage('Success!  You are now subscribed to the newsletter.');
  };

  return (
    <form onSubmit={subscribe}>
      <label htmlFor="email-input">{'Email Address'}</label>
      <input
        id="email-input"
        name="email"
        placeholder="you@awesome.com"
        ref={inputEl}
        required
        type="email"
      />
      <div>
        {message
          ? message
          : `I'll only send emails when new content is posted. No spam.`}
      </div>
      <button type="submit">{'subscribe '}</button>
    </form>
  );
}
```

<!--EndFragment-->