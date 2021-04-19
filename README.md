# Vnc
Install VNC Ubuntu 20.04


_sudo apt update_

sudo apt install lightdm

sudo apt install x11vnc

x11vnc


sudo nano /lib/systemd/system/x11vnc.service

[Unit]
Description=x11vnc service
After=display-manager.service network.target syslog.target

[Service]
Type=simple
ExecStart=/usr/bin/x11vnc -forever -display :0 -auth guess -passwd password
ExecStop=/usr/bin/killall x11vnc
Restart=on-failure

[Install]
WantedBy=multi-user.target

systemctl daemon-reload
systemctl enable x11vnc.service
systemctl start x11vnc.service


Privacidad – Bloqueo de pantalla - Deshabilitar
