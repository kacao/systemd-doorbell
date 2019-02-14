# systemd-doorbell
systemd script to start a doorbell service

```
[Unit]
Description=Doorbell

[Service]
Type=oneshot
ExecStart=/bin/sh -c "echo OFF > python3 /home/pi/doorbell/doorbell.py -d /bells"
ExecStop=/bin/sh -c "echo ON > pkill -f 'python3 doorbell.py'"
RemainAfterExit=yes

[Install]
WantedBy=multi-user.target
