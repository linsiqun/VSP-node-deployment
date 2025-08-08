<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Release port</strong> 
	</h1>
<a id="user-content-release-port" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#release-port"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw allow 80   #Very important
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw allow 443   #Very important
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	firewall-cmd --zone=public --add-port=Port number/tcp - Port number      #Release port1
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	iptables -A INPUT -p tcp --dport Port number -j ACCEPT     #Release port2
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw allow Port number     #Release port3
</p>
<p style="text-indent:2em;">
	<br />
</p>
<hr />
<p>
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Turn off the firewall</strong> 
	</h1>
<a id="user-content-turn-off-the-firewall" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#turn-off-the-firewall"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	systemctl stop firewalld.service    #Turn off the firewall1
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	service iptables stop   #Turn off the firewall2
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw disable    #Turn off the firewall3
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Midway deployment-build one-click script</strong> 
	</h1>
<a id="user-content-midway-deployment-build-one-click-script" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#midway-deployment-build-one-click-script"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	Update the system
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	yum install screen   #centos system
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	apt-get install wget     #wget system
</p>
<p style="text-indent:2em;">
	<strong><br />
</strong>
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	wget -N --no-check-certificate <a href="https://github.com/ginuerzh/gost/releases/download/v2.11.0/gost-linux-amd64-2.11.0.gz">https://github.com/ginuerzh/gost/releases/download/v2.11.0/gost-linux-amd64-2.11.0.gz</a> &amp;&amp; gzip -d gost-linux-amd64-2.11.0.gz     #[Deploy one-click script midway]
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	wget --no-check-certificate -O gost.sh <a href="https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh">https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh</a> &amp;&amp; chmod +x gost.sh &amp;&amp; ./gost.sh     #[Deploy the final script code]
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	mv gost-linux-amd64-2.11.0 gost      #Named gost
</p>
<p style="text-indent:2em;">
	chmod +x gost      #Add executable permissions to the gost file
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	./gost -L udp://:38420 -L tcp://:38420 -F 
relay+tls://Terminal:33280 &gt;&gt; /dev/null 2&gt;&amp;1 &amp;    
#Midway replacement code
</p>
<p style="text-indent:2em;">
	./gost -L relay+tls://:8888/To add the of the Terminal 
server code:443 &gt;&gt; /dev/null 2&gt;&amp;1 &amp;    #Terminal 
replacement code
</p>
<p style="text-indent:2em;">
	./gost.sh       #Management script commands
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Transfer midway One-click installation of Nodepass panel 2025</strong> 
	</h1>
<a id="user-content-transfer-midway-one-click-installation-of-nodepass-panel-2025" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#transfer-midway-one-click-installation-of-nodepass-panel-2025"></a> 
</div>
<p style="text-indent:2em;">
	Preparation
</p>
<p style="text-indent:2em;">
	Prepare two VPSs: one for the intermediate server and one for the terminal server.
</p>
<p style="text-indent:2em;">
	Deploy the corresponding nodes on the terminal server in advance. Install the 3X-UI panel on the terminal server in advance.
</p>
<p style="text-indent:2em;">
	Set up domain name resolution for the intermediate server and the terminal server in advance.
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	1、Apply for an SSL certificate with one click：【<a href="https://github.com/slobys/docker%E3%80%91">https://github.com/slobys/docker】</a> 
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -fsSL <a href="https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh">https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh</a>)    #Deployment Commands
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	2、Open Source Projects Nodepass：【<a href="https://github.com/yosebyte/nodepass%E3%80%91">https://github.com/yosebyte/nodepass】</a> 
</p>
<p style="text-indent:2em;">
	Nodepass Panel Project：【<a href="https://github.com/NodePassProject/npsh%E3%80%91">https://github.com/NodePassProject/npsh】</a> 
</p>
<p style="text-indent:2em;">
	A. Main program installation [Mid-range and terminal installation]
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(wget -qO- <a href="https://run.nodepass.eu/np.sh">https://run.nodepass.eu/np.sh</a>)    #Deployment Commands
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	B. Deploy Nodepass Panel [Mid-range terminal installation]
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(wget -qO- <a href="https://run.nodepass.eu/dash.sh">https://run.nodepass.eu/dash.sh</a>)    #Deployment Commands
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	One-click installation script [ terminal installation selection]
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -Ls <a href="https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh">https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh</a>)    #3X-UI one-click installation panel
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(wget -qO- <a href="https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh">https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh</a>)    #Sing-Box One-click script
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	4、The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	==========
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Midway one-click installation of Aurora Panel 2025</strong> 
	</h1>
<a id="user-content-midway-one-click-installation-of-aurora-panel-2025" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#midway-one-click-installation-of-aurora-panel-2025"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw disable    #Turn off the firewall
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -fsSL <a href="https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh">https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh</a>)    #One-click installation of Aurora panel midway
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	<br />
</p>
<hr />
<p>
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Trojan Panel Installation Panel</strong> 
	</h1>
<a id="user-content-trojan-panel-installation-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#trojan-panel-installation-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	apt update -y     #Update the system
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	apt-get install ca-certificates wget -y &amp;&amp; update-ca-certificates   #Update the system's root certificate
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	wget -O tcp.sh "<a href="https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh">https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh</a>" &amp;&amp; chmod +x tcp.sh &amp;&amp; ./tcp.sh    #Enable BBR acceleration
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	source &lt;(curl -L <a href="https://github.com/trojanpanel/install-script/raw/main/install%5C_script.sh">https://github.com/trojanpanel/install-script/raw/main/install\_script.sh</a>)     #Trojan Panel Installation Panel
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	Default login account: sysadmin Default login password: 123456
</p>
<p style="text-indent:2em;">
	Recommended installation order: Trojan Panel Backend &gt; Trojan Panel Frontend -&gt; Trojan Panel Cor
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>One-click installation of Sing-Box panel</strong> 
	</h1>
<a id="user-content-one-click-installation-of-sing-box-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#one-click-installation-of-sing-box-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -fsSL <a href="https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh">https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh</a>)      #Apply for an SSL certificate with one click
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -Ls <a href="https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh">https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh</a>)      #One-click installation of Sing-Box and Xray panels
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	<br />
</p>
<hr />
<p>
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>sb one-click deployment builds sing-box script</strong> 
	</h1>
<a id="user-content-sb-one-click-deployment-builds-sing-box-script" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#sb-one-click-deployment-builds-sing-box-script"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	sudo ufw disable    #Turn off the firewall
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(wget -qO- <a href="https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh">https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh</a>)   #sb one-key script
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Install x-ui panel</strong> 
	</h1>
<a id="user-content-install-x-ui-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#install-x-ui-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	ufw disable    #Turn off the firewall
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -Ls <a href="https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh">https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh</a>)      #Install x-ui panel
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Install 3x-ui panel</strong> 
	</h1>
<a id="user-content-install-3x-ui-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#install-3x-ui-panel"></a> 
</div>
<p style="text-indent:2em;">
	3X-UI open source project address: <a href="https://github.com/MHSanaei/3x-ui">https://github.com/MHSanaei/3x-ui</a> 
</p>
<p style="text-indent:2em;">
	Download and install the SSH connection tool Finalshell：<a href="https://www.hostbuf.com/t/988.html">https://www.hostbuf.com/t/988.html</a> 
</p>
<p style="text-indent:2em;">
	Server: 1-core, 1G 4T Debian system
</p>
<p style="text-indent:2em;">
	First, update the Debian/Ubuntu system and install components.
</p>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	<strong><br />
</strong>
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	apt update -y &amp;&amp; apt install curl sudo wget git -y
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	One-click installation script
</p>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	<br />
</p>
<p style="text-indent:2em;">
	bash &lt;(curl -Ls <a href="https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh">https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh</a>)
</p>
<p style="text-indent:2em;">
	<br />
</p>
<br />
<ol>
	<li>
		<p>
			Apply for an SSL certificate (disable the firewall (sudo 
ufw disable)/allow access to port 80 (ufw allow 80) for the certificate 
application to succeed).
		</p>
	</li>
	<li>
		<p>
			Configure the node (Important: If the node cannot access the internet, remember to allow access to the node port.)
		</p>
	</li>
</ol>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	①vless+grpc+reality  80
</p>
<p style="text-indent:2em;">
	②vless+tcp+reality
</p>
<p style="text-indent:2em;">
	②vless+xhttp+reality
</p>
<p style="text-indent:2em;">
	③vless+ws+tls  443
</p>
<p style="text-indent:2em;">
	④vless+tcp+tls
</p>
<p style="text-indent:2em;">
	<br />
</p>
<ol>
	<li>
		Enable BBR
	</li>
</ol>
<p>
	<br />
</p>
