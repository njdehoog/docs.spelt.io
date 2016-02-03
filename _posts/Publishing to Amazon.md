---
layout: post
title: Publishing to Amazon
date: 2016-01-29 12:39:20 +0100
category: publishing
permalink: amazon
---

Spelt allows you to publish your blog directly to [Amazon S3](http://aws.amazon.com/s3/). Amazon provides professional hosting for static websites through their S3 service, which is reliable, inexpensive and fast. If you have a custom domain you'd like to use, Spelt can even configure this domain to work with your site using [Amazon Route 53](http://aws.amazon.com/route53/).

## Create an account
	
To get started using Amazon S3, you should sign up for Amazon Web Services (AWS). To start the sign-up process, go [here](http://aws.amazon.com/s3/).

If you already have an AWS account, you can skip this step.

## Create access credentials

In order for Spelt to automatically deploy and configure your static website, it needs an __access and secret key__ (with S3 and Route53 permissions).

To create the necessary credentials, follow these steps:

1. Sign in to the [IAM management console](https://console.aws.amazon.com/iam).
2. Select `Users > Create New Users`
3. Pick a username to which these credentials will belong (e.g. Spelt).
4. Make sure the option: _Generate an access key for each user_ is selected and click `Create`
5. On the next page, click `Download Credentials` and make sure to store them in a safe place. You'll need these later on.
6. Close the wizard and select the user you just created. In the permissions tab, click `Attach Policy`.
7. Select _AmazonS3FullAccess_ and _AmazonRoute53FullAccess_ and click `Attach Policy`. Your user is now configured to access the necessary services.

## Publish

You are now ready to publish to Amazon. Open Spelt and select `Blog > Publish`. In the dialog that appears, enter the __Access Key ID__ and __Secret Access Key__ that you generated in the previous step. Spelt will store your `Secret Access Key` in your Keychain to keep it safe.


### Bucket name

Choose a unique bucket name for your site. Think of this as a folder that Spelt will upload your static site to. The bucket namespace is shared between all S3 users, so make sure to pick a unique name. If you want link a custom domain to your site, enter the domain name as your bucket name. So for _example.com_, your bucket name should also be _example.com_. More info on configuring a custom domain for your site can be found [here](/custom-domains/).