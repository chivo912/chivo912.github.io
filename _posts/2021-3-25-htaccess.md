---
layout: post
title: Some tips with .htaccess
---

### Angular
<pre>
RewriteEngine on
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_URI} !index
RewriteRule (.*) index.html [L]
</pre>

### Laravel
```
RewriteEngine On
RewriteRule ^(.*)$ public/$1 [L]
```

### Deny access for hidden files
```
RewriteCond %{SCRIPT_FILENAME} -d [OR]
RewriteCond %{SCRIPT_FILENAME} -f
RewriteRule "(^|/)\." - [F]
```

### Disable Directory Browsing
`Options All -Indexes`