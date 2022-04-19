# SYSTEMD SERVICE
## Create file shell script (.sh): 
```
sudo nano <path-to-file>/job.sh
```
>note: sudo apt install nano

## Add the following sample script:
```
#!/bin/bash
python3 python_script.py
```
## Save the script and execute permission:
```
sudo chmod u+x /home/rtr/projectexample/job.sh
```
## Create Service File:
```
sudo nano /etc/systemd/system/shellscript.service
```
##Add the following sample service:
```
[Unit]
Description=My Shell Script

[Service]
ExecStart=/bin/bash {path}/shellscript.sh
Restart=always
RestartSec=3
User=rtr

[Install]
WantedBy=multi-user.target
```
## Enable new service:
```
sudo chmod u+x /etc/systemd/system/shellscript.service
systemctl --user daemon-reload 
systemctl enable shellscript.service 
sudo systemctl start shellscript.service 

sudo systemctl stop shellscript.service # this function make stop service
```
## Verify the script:
```
sudo systemctl status shellscript.service 
```

# SYSTEMD TIMER
```
[Unit] 
Description=Runs the minetest.service 1 minute after boot up

[Timer] 
OnBootSec=1 m 
Unit=minetest.service 

[Install] 
WantedBy=basic.target
```