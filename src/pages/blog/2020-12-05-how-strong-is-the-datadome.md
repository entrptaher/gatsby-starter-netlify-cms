---
templateKey: blog-post
title: How strong is the Datadome?
date: 2020-12-05T07:21:31.904Z
description: Can you break their protection?
featuredpost: false
featuredimage: /img/1_twx6imcul-3kjqtx1t-_ag.png
tags:
  - automatio
  - datadome
---
Datadome is a Real-Time Bot Protection service. They are very proud of their bot detection technology and their blog has tons of information for the customers and scrapers.

I will share my viewpoint as someone who has been writing scraping scripts since I was a kid and also worked on several security aspects of different projects.

Web scraping and bot-protection, both are arts. They are two sides of the same coin. **You need to collect data from others while protecting yours.** It’s a bit of a grey area if you ask me 😏.

# Who is DataDome?

Big companies like TripAdvisor, Rakuten, classmates, Celio, Fnac, etc use Datadome to protect their website. Anyone who tried to create a bot for these websites had a little bit of hard time playing cat and mouse all the time.

The Datadome stuff regularly reads and analyses puppeteer-stealth and all different anti-bot detection posts on the internet, then applies it in their system. A pretty effective way to deal with the bots. 😎

They say they [apply statistical and behavioral detection](https://datadome.co/bot-management-protection/bot-detection-how-to-identify-bot-traffic-to-your-website/), can also [detect playwright](https://datadome.co/bot-detection/will-playwright-replace-puppeteer-for-bad-bot-play-acting/), implemented [client-side detection](https://datadome.co/bot-detection/client-side-detection-is-essential-for-bot-protection/), and so on 🔥.

It’s very important to pick know your enemy and your tool carefully. But…

![Image for post](https://miro.medium.com/max/576/0*LkgIaWkVfAICjefE.jpg)

So I decided to put it on two little tests. One is with normal means, and another is with the latest web automation tools.

# What inside the test?

For the sake of the test, it will go to their WordPress website hosted on the website at [https://datadome.co](https://datadome.co./)

Once detected, it will simply show a page with a custom captcha that cannot be solved by normal captcha solutions. No fancy ReCaptcha or Hcaptcha. Pretty impressive.

## Example of blocked version

![Image for post](https://miro.medium.com/max/1164/1*eiBhEBrZ880zqsZYsrzVBQ.png)

## Example of Non-blocked version

![Image for post](https://miro.medium.com/max/1182/1*AJrQegLx9QrRBPkE0UCH6Q.png)

# The Test — Part 1

I will just use some screenshot and page speed testing services. Usually these services use headless browsers to create the data, but some of these are also advanced, use various techniques to avoid detection.

And the results were not that much shocking,

> 9 out of 12 was blocked by the datadome protection.

Here are the sites that worked and the ones that did not.

## Performance Tools

✅ [KeyCDN](https://bit.ly/keycdnfree)

✅ Pingdom

❌ Google page speed insights

❌ Gtmetrix

❌Webpagetest

## Website Screenshot Tools

✅ Site Shot

❌ Screenshot Machine

❌Webcapture

❌Capturefullpage

❌Url2Png

❌SmallSeoTools

❌Page2Image

The protection is not without the tradeoff though.

They are expensive, even the starter package is $1190/mo. You cannot even protect your SPA or mobile until you pay $5990/mo. They only target big customers which is understandable. But it’s a no go for small businesses.

# The Test — Part 2

The test will be very simple. We will need to write our script if needed, or maybe use a click and point solution where everything is handled behind the back.

😎 Bots are getting intelligent and with a **combination of Residential IP and Stealth**, it can get away normally.

😈 The only time it would get detected if the IP/fingerprint is already **blacklisted** or if the scraping was done very **aggressively**. Whatever is the case, getting aggressive is never good.

And the results were not that much shocking for scrapers, but might shock the datadome customers.

> 3 out of 3 bypassed the datadome protection.

# ✅ [ScraperAPI](https://bit.ly/scraperapifree)

🔗 [Link](https://bit.ly/scraperapifree) 🕶 Failed once, passed all other times.

📜ScraperAPI service is pretty simple, you can use them as a proxy or normal scraper, it will return you the HTML source code of the service with residential IP, can render javascript and bypass lots of simple bot detection services.

🤓 Developer Friendly. Use their ready-made API and toolkit.

![Image for post](https://miro.medium.com/max/1552/1*YGDsiytrN3fQMJQp7HFmjw.png)

A simple script for [ScraperAPI](https://bit.ly/scraperapifree)

It can be done with NodeJS or curl and many other SDK provided by their website. I’m doing the test with a curl request.

![Image for post](https://miro.medium.com/max/973/1*NvtlUElpARGierQqXYse3A.png)

Their website is around 1.4mb without CSS and other stuff, the screenshot shows it downloaded everything even if it was slow due to proxies. Datadome could not even detect them on normal mode, or render mode.

# ✅ [Apify](https://bit.ly/apifyfree)

🔗 [Link](https://bit.ly/apifyfree) 🕶 Failed once without stealth, passed all other times.

📜 Apify is the one-stop shop for all your web scraping, data extraction, and robotic process automation (RPA) needs. They provide ready-made tools, lots of libraries, developer-friendly toolkit.

🤓 Developer Friendly. Write the code yourself using its robust library.

![Image for post](https://miro.medium.com/max/1770/1*rVvVc28qk1YHlX_ziPG7lA.png)

I had to make sure to turn on both the **custom stealth** and **proxy** mode or it was getting blocked instantly.

![Image for post](https://miro.medium.com/max/1366/0*fExJCOCRhr-htLrq)

The output had a bit of a mismatch in the screenshots, but it still works.

# ✅ [Automatio](https://bit.ly/automatiofree)

🔗 [Link](https://bit.ly/automatiofree) 🕶 Failed on one custom provided IP, passed all other times.

📜 Automatio is a web automation tool without coding and in just a few clicks. You can mine data, scrape websites, build charts, widgets, and much more.

😎 User friendly. You need to click and point.

![Image for post](https://miro.medium.com/max/1255/1*9pt4-W6M40YQ4SSTxojwpw.png)

I could extract the HTML, screenshots, individual elements, whole raw data including images, and everything using mhtml(mime HTML — a type of webpage archive format) extraction.

You don’t have to write any code to extract/automate anything.

![Image for post](https://miro.medium.com/max/1473/1*tccMSondBXgwsizlhA_gLg.png)

A minimal dashboard with minimal output showing how it can bypass them.

# Finishing Thoughts

I will need to test it with more sites and tools, it will be fun to see how both parties deal with this problem.

Datadome is great against normal bots and DDoS attacks, but there will always be a different loophole no matter what. If they add more realistic protection, someone will find a way to mimic it more realistically.

If you are trying to collect data or automate a website protected by datadome, analyze their behavior carefully just like they analyze yours to protect their customers.

*Disclosure: Bear in mind that some of the links in this post are affiliate links and if you go through them to make a purchase I will earn a commission.*

*Also, I am one of the developers of Automatio which is listed above, and it’s closed beta, you can check it out at [automatio.co](https://bitly.com/automatiofree), and the [automatio community](https://community.vanila.io/automatio).*