---
layout: post
title: How to fix CWP install SSL error
---

### acme.sh is now using zerossl, change it to letsencrypt CA server
this is due to acme client changed the default CA to zerossl to change back to letsencrypt run the below command as root

`/root/.acme.sh/acme.sh --set-default-ca  --server  letsencrypt`
