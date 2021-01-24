---
layout: blog
title: Create React App  vs. Gatsby vs. Nextjs
date: 2021-01-24T07:55:01.454Z
---
If you're just getting started, you might have heard about these three options:

* [](https://nextjs.org/)[Create React App (CRA)](https://create-react-app.dev/)
* [Gatsby](https://www.gatsbyjs.org/)
* [](https://create-react-app.dev/)[Next.js](https://nextjs.org/)

However, it's not exactly clear when or why you would choose one over the other. This post will highlight the key similarities and differences between the three solutions.

## Next.js

Next.js is the React framework that evolves with your product.

* **Static Sites** – Blazing-fast JAMstack websites.
* **Server Side Rendering** – Great for SEO and load performance.
* **Pre-Rendering** – Best of both worlds. Blazing-fast website + scale traffic effortlessly.

Next is unique among front-end and JAMstack frameworks because it seamlessly allows developers to grow from static sites to server-rendered sites as requirements change. It's also rapidly growing in popularity.

* 350k+ Next.js devs (30% of all React devs)
* 60+ Alexa top 10k sites built using Next.js
* Over 35,000 production sites


* **Pros**
* ✅ Support for full applications, as well as static sites
* ✅ Incredible developer experience

**Cons**

* ⛔️ Framework-specific knowledge
* ⛔️ Server-rendering adds complexity

## Gatsby

The key difference between Next.js and Gatsby is that Gatsby doesn't use a server. While Gatsby's main use case is for static sites, it can also re-hydrate into a fully-functional React application. Many other Next.js vs. Gatsby comparisons miss the fact that Next.js can also be used as a static site generator

**Pros**

* ✅ Robust [plugin library](https://www.gatsbyjs.org/plugins/)
* ✅ Well-written documentation & tutorials

**Cons**

* ⛔️ GraphQL knowledge potentially needed
* ⛔️ Potentially large build times (e.g. lots of images/fetches)

## Create React App

CRA helps you get started building React apps immediately with client-side rendering (CSR). There's much less to digest and understand. Unfortunately, that also means there's less you get for free as you scale your application.

**Pros**

* ✅ Easiest to learn (no extra framework)
* ✅ Created & maintained by React team

**Cons**

* ⛔️ No server-side rendering
* ⛔️ No code-splitting out of the box ([can be configured](https://create-react-app.dev/docs/code-splitting/))

## Conclusion

Still not sure which one to choose? I would highly recommend reading [Rendering on the Web](https://developers.google.com/web/updates/2019/02/rendering-on-the-web) for a deep-dive on where your rendering logic should live.