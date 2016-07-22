---
layout: post
title: "Figuring out web site operations"
date: 2016-07-22 10:57:55 -0400
categories: 
---

One of the beauties (or pain) of doing everything yourself from scratch in running a website, is that you have to figure out a lot about how websites work at a basic level.  For 2 days I couldn't figure out how to simultaneously route both afterschoolio.com and www.afterschoolio.com to the same Amazon EC2 implementation of the sample website I had created.  

In the Amazon Route53 (their DNS service provider) service user guide, it talks about how you can use Alias records to map either the root domain OR a subdomain to the EC2 implementation, but when I tried to create 2 separate records to do both, it didn't work.  I guess what's already cool with their implementation is that I can point the domain name address to the EC2 implementation, and although the IP addresses are dynamic and change all the time, it will always update automagically.  

But after struggling with the good old trial & error, and trying more conventional Google queries yielded basic definitions of DNS terms like [this search results](https://support.dnsimple.com/articles/differences-between-a-cname-alias-url/)

I used a very long query
_"how to point subdomain to same AWS Elastic Beanstalk environment as apex"_ 

and landed on this page 

[http://www.mikemurry.com/custom-domain-elastic-beanstalk/](http://www.mikemurry.com/custom-domain-elastic-beanstalk/)

which was exactly what I needed - the solution was to create a static website using Amazon S3 and pointing the apex name to it, and then redirecting that traffic to the www. Alias, which is dynamically pointing to the EC2 environment.  

Anyway - thanks Mike Murry!  [https://twitter.com/mikemurry](https://twitter.com/mikemurry)