##putty

install
```
sudo npm install pm2 -g
```
commands
```
pm2 list
pm2 status
pm2 stop my-app
pm2 restart my-app
pm2 delete my-app
pm2 logs
```
configuration for auto-start after server reboot.  
```
pm2 start npm --name my-app -- run start // we need to stay in the my-app directory.
```
Save the PM2 process list to the startup scripts:
```
pm2 save
```
Check that the startup script is generated:
```
ls /etc/systemd/system/
```
This command will list all the startup scripts in the `/etc/systemd/system/` directory. You should see a file called `pm2-root.service`.

Enable the PM2 startup script:
```
systemctl enable pm2-root.service
```
