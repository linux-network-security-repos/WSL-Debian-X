#!/bin/bash
sudo apt install dbus-x11 dbus -y
sudo service dbus start
sudo systemd-machine-id-setup
sudo dbus-uuidgen --ensure=/etc/machine-id
export DISPLAY=:0
export LIBGL_ALWAYS_INDIRECT=1
bash -l -c "sudo /etc/init.d/dbus start"
bash -l -c "DISPLAY=:0 dbus-launch --autolaunch $(cat /etc/machine-id) --binary-syntax --close-stderr"
bash -l -c "DISPLAY=:0 gnome-terminal"
chmod u+s /usr/bin/Xorg
./start-xfce
