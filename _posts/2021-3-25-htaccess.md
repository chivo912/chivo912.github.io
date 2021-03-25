---
layout: post
title: Some tips with .htaccess
---

### Angular
    RewriteEngine on
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_URI} !index
    RewriteRule (.*) index.html [L]

### Laravel
```json
RewriteEngine On
RewriteRule ^(.*)$ public/$1 [L]
```

### Deny access for hidden files
```php
RewriteCond %{SCRIPT_FILENAME} -d [OR]
RewriteCond %{SCRIPT_FILENAME} -f
RewriteRule "(^|/)\." - [F]
```

### Disable Directory Browsing
`Options All -Indexes`


### Flow chart sample
```flow
st=>start: Login
op=>operation: Login operation
cond=>condition: Successful Yes or No?
e=>end: To admin

st->op->cond
cond(yes)->e
cond(no)->op
```