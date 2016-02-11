---
layout: post
title: Custom domains
date: 2015-01-29 13:21:46 +0100
category: publishing
permalink: custom-domains
---

When you publish your blog you'll probably want to make it reachable under a custom domain name, instead of the S3 URL that is provided by Amazon. Spelt streamlines this process by configuring the DNS settings for your domain using [Amazon Route 53](http://aws.amazon.com/route53/).

To enable this functionality, make sure to check the _Use Amazon Route 53_ option in the publish dialog.

> When this option is enabled, your bucket name should reflect the domain name you want to use, e.g. the bucket name for this website is `docs.spelt.io`

## Change the name servers for your domain

The last step is to change the name servers for your domain. At the end of the publishing process, Spelt provides four NS records, which you'll need to copy and paste into your domain registrars management panel. Doing this ensures that traffic for your domain will be routed through Amazon Route 53. Keep in mind that it might take some time for these settings to take effect.

> If you have any existing DNS records for your domain that you want to remain in effect, make sure to copy those over to Amazon Route 53 using the [admin console](https://console.aws.amazon.com/route53). Navigate to _Hosted Zones_ and select your domain name to add or edit individual DNS records.
