---
layout: post
title: Some MySQL Tips!
---

### Replace email domain
`UPDATE personal SET email = REPLACE(email, SUBSTRING_INDEX(email, '@', -1), 'yopmail.com')`

### Get email domain
`SELECT DISTINCT SUBSTRING(email,INSTR(email,'@')+1) AS domain FROM personal;`
