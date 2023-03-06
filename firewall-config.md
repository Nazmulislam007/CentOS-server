# allow traffic on port
## Firewall settings are important for securing your server and allowing or blocking access to certain services and ports

Check if firewalld is installed and running:
```
sudo systemctl status firewalld
```
If it's not running, start the service:
```
sudo systemctl start firewalld
```
Add the port 3000 to the firewall:
```
sudo firewall-cmd --add-port=3000/tcp --permanent
```

This will add a permanent rule to allow incoming TCP traffic on port 3000.

Reload the firewall to apply the changes:
```
sudo firewall-cmd --reload
```
Now, incoming traffic on port 3000 should be allowed through the firewall.
