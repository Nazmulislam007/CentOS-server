show list
```
pm2 list
```
run pm2
```
pm2 start npm --name my-app -- run start
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
