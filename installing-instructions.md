# Run the commands below to install WSL2 Ubuntu GUI
### Installing required modules
- sudo apt update && sudo apt -y upgrade
- sudo apt install xrdp
- sudo apt install -y xfce4
- select gdm3 as GUI
- sudo apt install -y xfce4-goodies
- sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
- sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
- sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
- echo xfce4-session > ~/.xsession
- sudo nano /etc/xrdp/startwm.sh
- Edit startwm.sh as following
- comment out: test -x /etc/X11/Xsession && exec /etc/X11/Xsession
- comment out: exec /bin/sh /etc/X11/Xsession
- add: xfce
- add: startxfce4
- save file:
### Connect to remote server
- sudo /etc/init.d/xrdp start
### Open Remote Desktop Connection localhost:3390




