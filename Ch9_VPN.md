# 第9章 黑帽駭客 (Black Hats)? 又該如何抵擋 (How To Defeact)? VPN? Plan

## 實戰: C1 快速而輕鬆地確定您的 IP 位址的工具, C2. Intall VPN and use it on MSWindows 

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/47ee7460-3cd8-4881-8196-6eea8b6070a3)

1. OpenVPN Connect for Windows, https://openvpn.net/client/client-connect-vpn-for-windows/

2. 免費VPN節點, [https://www.freedidi.com/2690.html](https://www.vpnbook.com/freevpn)

OpenVPN is the best and most recommended open-source VPN software world-wide. It is the most secure VPN option. You need to download the open-source OpenVPN Client and our configuration and certificate bundle from the links below (use TCP if you cannot connect to UDP due to network restriction).

OpenVPN config updated on 2023/02/24. Download new bundles below:
PL226 OpenVPN Bundle
DE4 OpenVPN Bundle
(Following servers are optimized for fast web surfing; no p2p downloading)
US1 OpenVPN Bundle
US2 OpenVPN Bundle
CA222 OpenVPN Bundle
CA198 OpenVPN Bundle
FR1 OpenVPN Bundle
FR8 OpenVPN Bundle
All bundles include UDP53, UDP 25000, TCP 80, TCP 443 profile
Username: vpnbook
Password: [check](https://www.vpnbook.com/freevpn)


## C3. Linux下載安裝OpenVPN 服務端 （一鍵安裝命令）, https://www.freedidi.com/2694.html


1. wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh

2. 輸入一鍵安裝安裝命令以後回車確認，協議類型選擇1：UDP

3. 埠默認1194 或者其它，DNS選擇OpenDNS

4. https://winscp.net/eng/download.php
