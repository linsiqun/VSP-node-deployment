# **Release port**


ufw allow 80   #Very important



ufw allow 443   #Very important



firewall-cmd --zone=public --add-port=Port number/tcp - Port number      #Release port1



iptables -A INPUT -p tcp --dport Port number -j ACCEPT     #Release port2



ufw allow Port number     #Release port3


--------


# **Turn off the firewall**


systemctl stop firewalld.service    #Turn off the firewall1



service iptables stop   #Turn off the firewall2



ufw disable    #Turn off the firewall3


==========


# **Midway deployment-build one-click script**


Update the system


apt update -y \&\& apt install curl sudo wget git -y    #Debian/Ubuntu system



yum install screen   #centos system



apt-get install wget     #wget system



wget -N --no-check-certificate https://github.com/ginuerzh/gost/releases/download/v2.11.0/gost-linux-amd64-2.11.0.gz \&\& gzip -d gost-linux-amd64-2.11.0.gz     #[Deploy one-click script midway]


wget --no-check-certificate -O gost.sh https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh \&\& chmod +x gost.sh \&\& ./gost.sh     #[Deploy the final script code]



The router client replaces the transfer machine IP address and port



mv gost-linux-amd64-2.11.0 gost      #Named gost



chmod +x gost      #Add executable permissions to the gost file



./gost -L udp://:38420 -L tcp://:38420 -F relay+tls://Terminal:33280 >> /dev/null 2>\&1 \&    #Midway replacement code


./gost -L relay+tls://:8888/To add the of the Terminal server code:443 >> /dev/null 2>\&1 \&    #Terminal replacement code 



./gost.sh       #Management script commands


==========


# **Transfer midway One-click installation of Nodepass panel 2025**

Preparation

Prepare two VPSs: one for the intermediate server and one for the terminal server.

Deploy the corresponding nodes on the terminal server in advance. Install the 3X-UI panel on the terminal server in advance.

Set up domain name resolution for the intermediate server and the terminal server in advance.


1、Apply for an SSL certificate with one click：【https://github.com/slobys/docker】


bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)    #Deployment Commands



2、Open Source Projects Nodepass：【https://github.com/yosebyte/nodepass】

Nodepass Panel Project：【https://github.com/NodePassProject/npsh】



A. Main program installation [Mid-range and terminal installation]


bash <(wget -qO- https://run.nodepass.eu/np.sh)    #Deployment Commands



B. Deploy Nodepass Panel [Mid-range terminal installation]


bash <(wget -qO- https://run.nodepass.eu/dash.sh)    #Deployment Commands



One-click installation script [ terminal installation selection]


bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)    #3X-UI one-click installation panel


bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)    #Sing-Box One-click script



4、The router client replaces the transfer machine IP address and port


==========

# **Midway one-click installation of Aurora Panel 2025**


ufw disable    #Turn off the firewall



bash <(curl -fsSL https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh)    #One-click installation of Aurora panel midway



The router client replaces the transfer machine IP address and port


--------


# **Trojan Panel Installation Panel**

apt update -y     #Update the system



apt-get install ca-certificates wget -y \&\& update-ca-certificates   #Update the system's root certificate



wget -O tcp.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh" \&\& chmod +x tcp.sh \&\& ./tcp.sh    #Enable BBR acceleration


source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install\_script.sh)     #Trojan Panel Installation Panel



Default login account: sysadmin Default login password: 123456


Recommended installation order: Trojan Panel Backend > Trojan Panel Frontend -> Trojan Panel Cor


==========


# **One-click installation of Sing-Box panel**


bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)      #Apply for an SSL certificate with one click



bash <(curl -Ls https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh)      #One-click installation of Sing-Box and Xray panels


--------


# **sb one-click deployment builds sing-box script**


sudo ufw disable    #Turn off the firewall



bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)   #sb one-key script


==========


# **Install x-ui panel**


ufw disable    #Turn off the firewall



bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)      #Install x-ui panel


==========


# **Install 3x-ui panel**


3X-UI open source project address: https://github.com/MHSanaei/3x-ui



Download and install the SSH connection tool Finalshell：https://www.hostbuf.com/t/988.html



Server: 1-core, 1G 4T Debian system


1. First, update the Debian/Ubuntu system and install components.


apt update -y \&\& apt install curl sudo wget git -y



2. One-click installation script


bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)


3. Apply for an SSL certificate (disable the firewall (sudo ufw disable)/allow access to port 80 (ufw allow 80) for the certificate application to succeed).


4. Configure the node (Important: If the node cannot access the internet, remember to allow access to the node port.)



①vless+grpc+reality  80


②vless+tcp+reality


②vless+xhttp+reality


③vless+ws+tls  443


④vless+tcp+tls


5. Enable BBR


==================================
