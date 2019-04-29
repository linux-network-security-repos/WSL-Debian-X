# Fixing The Broken Dbus in WSL

Running this code and praying like hell this works!

```
sudo apt install dbus-x11
sudo systemd-machine-id-setup
export DISPLAY=localhost:0
sudo apt install dbus-x11 dbus -y
sudo service dbus start
sudo systemd-machine-id-setup
sudo dbus-uuidgen --ensure=/etc/machine-id
export DISPLAY=localhost:0
export LIBGL_ALWAYS_INDIRECT=1
```



Older instructions (for previous iterations of Windows 10 and Ubuntu) required the dbus listen directive to point to tcp:host=localhost..., and that no longer works. If you have some old change to that around (/etc/dbus-1/session.conf or /usr/share/dbus-1/session.conf), it should be set-back to default <listen>unix:tmpdir=/tmp</listen>.

```
bash -l -c "sudo /etc/init.d/dbus start"
bash -l -c "DISPLAY=:0 dbus-launch --autolaunch $(cat /etc/machine-id) --binary-syntax --close-stderr"
bash -l -c "DISPLAY=:0 gnome-terminal"
```
