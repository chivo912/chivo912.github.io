---
layout: post
title: How to install SSL with cerbot-auto
---

### Install/Renew SSL for all subdomains via DNS
`certbot-auto certonly --manual --preferred-challenges dns -d *.yourdomain.com -d yourdomain.com`

### Install/Renew SSL for single domain (Apache)
`certbot-auto --apache -d uat.stambridge.group`