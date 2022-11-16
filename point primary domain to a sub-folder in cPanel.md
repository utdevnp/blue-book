RewriteEngine on
RewriteCond %{HTTP_HOST} ^spnepal.org$ [NC,OR]
RewriteCond %{HTTP_HOST} ^www.domainl.org$
RewriteCond %{REQUEST_URI} !folder/
RewriteRule (.*) /folder/$1 [L]
