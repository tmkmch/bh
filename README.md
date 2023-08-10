# Bandwidth Hero Data Compression Service

Welcome to the **Serverless** port of Bandwidth Hero Data Compression Service 🚀. This service is designed to compress images on the fly, saving you bandwidth and improving your browsing experience.

To get started with deploying your own instance of this service, please follow the detailed instructions in the #Deployment section below.

**एक मिनट से भी कम समय में इसे deploy करें , उस के लिए #Deployment अनुभाग पढ़ें।**

Currently using Netlify functions, which has a genorous limit of calls you can make, mostly enough for personal use, or small scale use, for faster and much more users, a dedicated server (code on original repo) maybe preferable :D

The original and this fork, both are, data compression service used by [Bandwidth Hero](https://github.com/ayastreb/bandwidth-hero) browser extension. It compresses (optionally grayscale) given image to low-res [WebP](https://developers.google.com/speed/webp/) or JPEG image.

It downloads original image and transforms it with [Sharp](https://github.com/lovell/sharp) on the fly without saving images on disk.

**Benefits** - It's faster for initial requests, as it doesn't require restarting a sleeping heroku server deployment, also, you may benefit from a better ping (in my case it is such)

> Note: It downloads images on user's behalf (By passing in same headers to the domain with required image), passing cookies and user's IP address through to the origin host.

## Deployment

I can't provide you with my deployment, since I have the free tier, and that has it's limits.

You need to deploy the functions to Netlify:

[![Deploy](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/himshim/bandwidth-hero-proxy2)

Then, in the **Data Compression Service** in Bandwidth Hero extension, add `https://your-netlify-domain.netlify.app/api/index`, and you are good to go.

<!-- READ THIS ARTICLE LATER AdityaG
Check out [this guide](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-16-04)
on how to setup Node.js on Ubuntu. 
DigitalOcean also provides an
[easy way](https://www.digitalocean.com/products/one-click-apps/node-js/) to setup a server ready to
host Node.js apps.
-->