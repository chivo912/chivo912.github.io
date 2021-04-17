---
layout: post
title: Bcrypt hash from command line
---

### Replace "password"
`htpasswd -bnBC 10 "" password | tr -d ':\n'`
