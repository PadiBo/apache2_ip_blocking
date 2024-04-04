move the ip_range.conf to your webserver path /etc/apache2/blocker/
edit your /etc/apache2/apache2.conf and add the following lines:

```
#IPBlocker
<Location />
   <RequireAll>
      Require all granted
      Include /etc/apache2/blocker/ipblacklist.conf
      Include /etc/apache2/blocker/ip_range.conf
   </RequireAll>
</Location>
```
All IPs and ranges tryed to access specific paths like phpmyAdmin or Login pages.
If you really want to annoy those fuckers, add this at the end of your apache2.conf:
```
#CUSTOM REDIRECT
ErrorDocument 400 "https://shattereddisk.github.io/rickroll/rickroll.mp4"
ErrorDocument 403 "https://shattereddisk.github.io/rickroll/rickroll.mp4"
ErrorDocument 404 "https://shattereddisk.github.io/rickroll/rickroll.mp4"
ErrorDocument 302 "https://shattereddisk.github.io/rickroll/rickroll.mp4"
```
If  one of the ips calls your webpage they get redirected to a rick roll.

Note:
You need to restart the apache2 server to make it work
