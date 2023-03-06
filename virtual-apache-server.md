# Virtual hosting in CentOS

Open the Apache configuration file for virtual hosts:
```
sudo nano /etc/httpd/conf/httpd.conf
```

Uncomment the following line to enable virtual hosting:
`# IncludeOptional conf.d/*.conf`
Should become:
```
IncludeOptional conf.d/*.conf
```
Create a new virtual host configuration file:
```
sudo nano /etc/httpd/conf.d/my-website.conf
```

Add the following configuration to the file, replacing 167.99.182.9 with your server's IP address and 3000 with the port in which app is running on:
```
<VirtualHost *:80>
    ServerName 167.99.182.9
    ProxyPreserveHost On
    ProxyPass / http://localhost:3000/
    ProxyPassReverse / http://localhost:3000/
</VirtualHost>
```

This configuration sets up a reverse proxy to forward requests from Apache to your app running on port 3000.

Save the file `ctrl X` `Y` `enter` and exit.

Enable the proxy and proxy_http Apache modules:
```
sudo a2enmod proxy
sudo a2enmod proxy_http
```

Test the configuration:
```
sudo apachectl configtest
```
If everything is okay, you should see `Syntax OK`.

Restart Apache to apply the changes:
```
sudo systemctl restart httpd
```
