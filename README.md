# WSL-Debian-X
Tweaks to run Debian Linux desktop panels and gui apps on Windows 10
Modified from my brother Re4son's version for Kali. This version is soon to be updated to fix many new bugs noticed in the last systemd updates from Stretch stable. I will make sure we are ready for sid buster and beyond. Why use a VM when you can make windows understand that you are a Toy Story fan?


### Installation:
1.  Start debian in Windows 10 as normal, unprivileged user
2.  Run

                ```
                
                wget https://raw.githubusercontent.com/diveyez/WSL-Debian-X/master/install-WSL-Debian-X
                bash ./install-WSL-Debian-X
                
                ```


3.  Download and install VcXsrv X Server from here:
    <https://sourceforge.net/projects/vcxsrv/>

### Starting the GUI:
As root:

                ```
                
                ~/start-xfce
                
                ```
                
As normal user:

                ```
                
                sudo /root/xtart-xfce
                
                ```

### Starting the full desktop and connecting to it via Remote Desktop Client:
1.  In the WSL session, run:

                           ```
                           
                           sudo /etc/init.d/xrdp start
                           
                           ```
                           
2.  Open Remote Desktop Connection (mstsc) and connect to 127.0.0.1:3390
3.  To close the xrdp server, type:
                           
                           ```
                           
                           sudo /etc/init.d/xrdp stop
                           
                           ```
