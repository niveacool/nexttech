sudo adduser nebula --gecos "First Last,RoomNumber,WorkPhone,HomePhone" --disabled-password
echo "nebula:eng1neer@@" | sudo chpasswd
sudo usermod -aG sudo,adm akuhnet
clear
rm -rf ngrok  ngrok.zip  ng.sh > /dev/null 2>&1
wget -O ng.sh https://bit.ly/ngrok3389 > /dev/null 2>&1
chmod +x ng.sh
./ng.sh
echo "===================================="
echo "Install XFCE"
echo "===================================="
sudo apt install -y xfce4 xfce4-goodies > /dev/null 2>&1
echo "=============50%"
sudo apt-get install -y xrdp > /dev/null 2>&1
echo "=================70%"
echo xfce4-session >~/.xsession
echo "=====================90%"
sudo service xrdp start
clear
echo "=======================100%"
echo "===================================="
echo "Username : nebula"
echo "Password : eng1neer@@"
echo "right click to open menu"
echo RDP Address:
curl --silent --show-error http://127.0.0.1:4040/api/tunnels | sed -nE 's/.*public_url":"tcp:..([^"]*).*/\1/p'
echo "===================================="
sleep 43210
