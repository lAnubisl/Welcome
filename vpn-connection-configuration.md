# VPN connection configuration

#### 1. Contact <giorgi.mukhigulashvili@lykke-business.ch> to get vpn access. Here is a email template:

Hello Giorgi.
My name is [YOUR NAME] and I’m working on a company [YOUR COMPANY NAME].
Our company is a partner of OpenMAVN and I have been assigned to OpenMAVN project.   

Please provide me with VPN access to the internal development kubernetes cluster.
Please also give me read only access to [Lykke Settings Service](http://settingsv2.settings.svc.cluster.local/Home/Repository).    

Best regards,
[YOUR NAME].

#### 2.  Once you get a reply with a ZIP file containing your VPN profile you should install the latest OpenVPN.
    

* For Windows: from here: [https://openvpn.net/community-downloads/](https://openvpn.net/community-downloads/)    

* For MacOS: from here:     

* For Linux: from here:
    

#### 3.  Import openvpn profile.
* Fow Windows: right click on OpenVPN Gui icon in a tray bar and select “import file”. Then select the “.ovpn” file that you get on step 2. The imported profile should be located in “C:\Users\[YOUR USER]\OpenVPN\config” directory. Make sure that the second file “.p12” which is your private key is also located there. If not then copy it there manually.    

* For MacOS:    

* For Linux:
    

#### 4.  Connect to the VPN server using your configuration.
    

* For Windows: click on OpenVPN Gui icon in a tray bar and select “Connect”. You should see the connection log window and then get windows notification “openmavn-vpn is now connected”.
    
* For MacOS:
    
* For Linux: