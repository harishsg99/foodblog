---
layout: blog
title: Account taker over using OTP bypass
date: 2021-06-22T11:01:23.578Z
---
<!--StartFragment-->

Hey folks, My name is Harish,I am back with one more interesting write up which i found in RDP. I will explain little bit about my methodology once I found the target to hunt first i will analyse the site like normal user by creating account and i will understand target by using it as normal user. After that i will start with my favorite bug, i.e account takeover.

As usual i was hunting for account takeover. I created two accounts and I click on forget password, after that i checked my mail there i got the code that time 2 tricks started running on my head

1.Response manipulation

2.OTP bypass by no rate limit

First I tried for response manipulation I entered wrong otp, i captured the request in burp suite, and i saw response, it was status code 400 bad request then i changed the response to 200 OK and success but bad luck not bypassed. i was like ok lets move to the second trick

Then I decided to brute force the OTP because it was 4 Digit code we can do it in short time, so I requested for new OTP without seeing OTP I entered one random OTP and Captured the request in burp and i sent it to intruder, there I added the number payload 0000 to 9999 and started attack.

![](https://miro.medium.com/max/60/1*T3OKN_dr8SNB5m_6am7KhQ.png?q=20)

![](https://miro.medium.com/max/1211/1*T3OKN_dr8SNB5m_6am7KhQ.png)

You can see the status code 200 here I bypassed the OTP successfully. Using this bug I can hack any users without user interaction.

Steps to reproduce:

steps to reproduce\

1. Go to [https://www.target.](https://www.dmart.in/)com (A Famous Indian Ecommerce website) \
2. Go for password reset option\
3. Enter the victims mail id\
4. Enter a random 4 digit OTP\
5. Capture the request in burp and send it to intruder\
6. Create the payload of 4 digit number and start the attack\
7. You can see the changes in the length and status code 200 OK\
8. Enter the correct OTP and change password of the victim account

<!--EndFragment-->