---
layout: post
title: How to prevent SSH from timing out
---

### Client Side Keep Alive
This method is set on your client machine which you’re using to connect to the server. If you’re using Linux, the method is similar to the Server Side steps with a couple of minor differences.

To set the SSH keep alive option on a Linux client:

- Log in as root
- Edit the file at /etc/ssh/ssh_config
- Add this line to the file: ServerAliveInterval 60
- Save the file