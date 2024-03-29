# 第6章 網路監聽 ( Network Tapping)

<a name="000"/>


## 目錄(Table of Contents)

[實戰1: 試介紹本章介紹的技術名詞與功用: 網路監聽, MAC地址, DNS, DoS, DMZ, Firewalls, IDS, IPS](#111)

[實戰2: 設置防火牆 (Setting Up Your Firewall) ](#222)

---

<a name="111"/>
## 實戰1: 試介紹本章介紹的技術名詞與功用

### 1. 網路監聽?
Ans.: 是一種監控、分析和管理電腦網路性能、運行狀況和資源使用情況的過程。網路監聽的主要目的是確保網路運行正常，並在出現問題時及時偵測和解決，以避免中斷或減少對用戶和應用程式的影響。網路監聽的主要功能包括：

故障檢測和排除：通過收集和分析網路活動數據，及時發現和解決硬體故障、配置錯誤和其他問題，以保證網路運行的穩定性和可靠性。

性能監控：評估網路設備和連接的性能，包括響應時間、吞吐量、資源使用率等，以確保網路能夠滿足用戶和應用程式的需求。

帶寬管理：監控網路上的流量和帶寬使用情況，以避免擁塞和確保關鍵應用程式的性能。

安全監控：檢測和防止網路上的惡意活動，如黑客攻擊、病毒和惡意軟體，以保護網路資源和數據的安全。

網路監聽工具和軟體可以實現以上功能。一些常見的網路監聽工具包括Wireshark、Nagios、PRTG Network Monitor等。網路管理員通常使用這些工具來監控網路設備和服務的運行狀況，以確保網路的正常運行和高效能。

![image](https://user-images.githubusercontent.com/55008636/236664488-39c34e24-13d6-4de7-9cee-fd21e4b0b101.png)


### 2. MAC地址?
Ans.: MAC 地址用於 OSI（開放系統互連）模型的數據鏈路層（第 2 層）以識別網絡中的設備。 它們對於局域網 (LAN) 內的通信至關重要，並且與設備的網絡接口卡 (NIC) 相關聯。

由於 MAC 地址對於每個網絡接口都是唯一的，因此它們可用於過濾、跟踪和保護網絡訪問。 例如，網絡管理員可以根據 MAC 地址配置訪問控制列表 (ACL)，以允許或拒絕特定設備訪問網絡。 但是，請務必注意 MAC 地址可能會被欺騙或更改，因此不建議僅依賴它們來確保網絡安全。

### 3. DNS
Ans.: DNS（域名系統）是一種用於將人類可讀的域名翻譯成計算機可以理解的IP（互聯網協議）地址的系統。 它的功能就像互聯網的電話簿，允許用戶使用域名訪問網站，而不是記住數字 IP 地址。 DNS 通過促進計算機和服務器之間的通信，在 Internet 的功能中起著至關重要的作用。

以下是 DNS 的三個經典示例：

1. 網站瀏覽：當您在 Web 瀏覽器中輸入域名（例如 www.example.com）時，瀏覽器會向 DNS 服務器發送查詢以將域名解析為 IP 地址。 一旦 DNS 服務器提供了 IP 地址，瀏覽器就可以與託管網站的 Web 服務器建立連接並請求網站的內容。

2. 郵件發送：當您向 someone@example.com 發送電子郵件時，您的電子郵件客戶端或服務器將查詢 DNS 系統以查找收件人郵件服務器的 IP 地址。 一旦獲得 IP 地址，電子郵件就可以傳送到收件人的郵件服務器，然後郵件服務器會將電子郵件路由到收件人的收件箱。

3.負載均衡和冗餘：DNS 可用於在託管相同網站或服務的多個服務器之間分配流量。 通過為單個域名提供多個 IP 地址，DNS 可以根據服務器負載、地理位置或可用性等因素將用戶定向到不同的服務器。 這有助於維持服務性能並在服務器出現故障時提供冗餘。

在所有這些示例中，DNS 充當了人類可讀域名和機器可讀 IP 地址之間的橋樑，簡化了訪問互聯網資源的過程。

![image](https://user-images.githubusercontent.com/55008636/236664566-5dbea2f4-8acf-4f07-b803-790e8a269bd1.png)

![image](https://user-images.githubusercontent.com/55008636/236664612-90e60682-c51d-4d87-91c5-bdac2408c83f.png)

### 4. 阻斷服務攻擊（DoS）
Ans.: 阻斷服務攻擊（DoS，Denial of Service）是一種網路安全攻擊，其目的是使目標系統、服務或網路資源無法正常運作，從而對正常使用者造成服務中斷。這種攻擊通常通過向目標系統發送大量的請求或數據包，使其資源耗盡或過載，無法繼續為正常使用者提供服務。

DoS攻擊的一種常見變體是分散式阻斷服務攻擊（DDoS，Distributed Denial of Service）。在DDoS攻擊中，攻擊者通過多個（有時數以萬計）受感染的電腦或設備（稱為「殭屍」或「僵屍網路」）同時發動攻擊，以加大對目標的影響。

![image](https://user-images.githubusercontent.com/55008636/236664764-d5f90a69-cfe5-4be5-9173-61b329c6d289.png)

### 5. 非軍事區 (DMZ)
Ans.: 非軍事區（DMZ，Demilitarized Zone）是一種網路安全架構，主要用於將內部網路（公司、政府或機構等）與外部網路（如互聯網）分開。這種架構的目的是在兩者之間建立一個緩衝區，以保護內部網路免受外部網路的攻擊或威脅。

在DMZ架構中，通常會設置一個或多個網路設備（如防火牆、路由器等），用於監控和控制網路流量。外部網路用戶只能訪問DMZ中的設備，而不能直接訪問內部網路。同樣，內部網路用戶也無法直接訪問外部網路，而必須經過DMZ中的設備。這樣可以有效地阻止潛在的攻擊者入侵內部網路，保護敏感資料和系統。

在DMZ中通常部署的設備包括網頁伺服器、郵件伺服器和其他對外提供服務的伺服器。這些伺服器為外部網路用戶提供所需的資源，同時遠離內部網路的核心資源。這樣，即使DMZ中的伺服器受到攻擊或遭受損壞，內部網路的其他部分也能保持安全。

![image](https://user-images.githubusercontent.com/55008636/236664857-bbc4a1f0-6212-4abf-a78d-4d8899951164.png)

### 6. 防火牆 (Firewalls)
Ans. 防火牆（Firewalls）是一種網路安全技術，用於監控並控制進入和離開網路的數據流量。它的主要目的是在內部網絡和外部網絡之間建立一道安全屏障，以保護內部網絡免受未經授權的訪問和惡意攻擊。防火牆可以是硬體、軟體或兩者的組合。

以下是防火牆的三個經典範例：

個人電腦防火牆：許多作業系統（例如Windows和macOS）內置了軟體防火牆，用於保護個人電腦免受外部威脅。這些防火牆允許用戶控制哪些應用程序可以訪問互聯網，並根據用戶定義的規則阻止或允許特定類型的流量。

企業網絡防火牆：企業和組織通常使用硬體防火牆來保護其內部網絡。這些防火牆通常安裝在網絡邊緣，作為企業網絡與互聯網之間的第一道防線。它們可以防止未經授權的訪問，並對通過防火牆的數據流量進行檢查以檢測和阻止惡意活動。

雲端防火牆：隨著企業和組織將其資源遷移到雲端，雲端防火牆成為一個越來越受歡迎的解決方案。雲端防火牆是一種基於雲的安全服務，可在雲端環境中提供防火牆功能。它們允許用戶集中管理和應用安全策略，並提供靈活性和可擴展性以滿足不斷變化的網絡需求。

這些例子展示了防火牆在不同場景中的應用，它們都旨在保護網絡免受未經授權的訪問和潛在的惡意攻擊。

![image](https://user-images.githubusercontent.com/55008636/236664923-2a1e94d5-bfaf-413e-9ee0-ded83965260f.png)

![image](https://user-images.githubusercontent.com/55008636/236665018-d75dd2f6-c0ef-4c0b-8695-c811dfbe04d0.png)


### 7. 入侵檢測系統 (IDS)
Ans.: 入侵檢測系統（Intrusion Detection System, IDS）是一種用於監控網路或系統活動的安全技術，用以檢測潛在的惡意行為、未經授權的訪問或政策違規行為。IDS 可以用來保護網路和資訊系統免受攻擊、妨礙和濫用。IDS 可分為兩大類：基於網路的入侵檢測系統（NIDS）和基於主機的入侵檢測系統（HIDS）。

以下是三個典型的入侵檢測系統實例：

Snort：Snort 是一款開源的網路入侵檢測系統，使用基於規則的檢測方法來監控網路流量，並在檢測到可疑活動時發出警報。Snort 可以檢測各種攻擊，如端口掃描、網絡蠕蟲和分散式拒絕服務（DDoS）攻擊。

OSSEC：OSSEC 是一款開源的基於主機的入侵檢測系統，適用於多個平台，如 Windows、Linux 和 macOS。OSSEC 通過分析系統日誌和應用程序日誌來檢測潛在的安全威脅。此外，OSSEC 還提供了完整性檢查、入侵檢測和實時警報功能。

Suricata：Suricata 是一款基於網路的入侵檢測和防護系統，它可以檢測多種攻擊，包括端口掃描、網絡蠕蟲、DDoS 攻擊等。Suricata 採用基於規則的檢測方法，並使用多核心處理技術來提高性能。它還支持實時分析和警報，以便在攻擊發生時立即採取行動。

以上例子顯示了入侵檢測系統在不同環境下的應用，通過不斷監控和分析網路或系統活動，為組織提供安全防護。

### 8. 入侵防禦系統 (IPS)
Ans.: 入侵防禦系統 (IPS, Intrusion Prevention System) 是一種網路安全技術，主要用於檢測和防止對網路及其資源的未經授權的存取和攻擊。IPS 是入侵偵測系統 (IDS) 的進階版本，除了檢測潛在的威脅外，還具有主動阻止和阻擾攻擊的功能。IPS 通常與防火牆結合使用，以提供更全面的網路保護。

以下是三個入侵防禦系統 (IPS) 的經典實例：

防止分散式阻斷服務 (DDoS) 攻擊：
IPS 可以識別來自大量來源的異常網路流量，這可能是分散式阻斷服務 (DDoS) 攻擊的徵兆。IPS 會主動阻止這些流量，以保護網站和其他網路資源免受攻擊。

防止惡意軟體傳播：
IPS 可以檢測嘗試將惡意軟體（如病毒、蠕蟲和特洛伊木馬）傳播到網路的攻擊。當 IPS 發現這些威脅時，它會阻止這些惡意軟體進入網路，以保護網路資源和用戶數據。

防止未經授權的存取：
IPS 可以檢測來自未經授權的來源的連接嘗試，如駭客或內部惡意用戶嘗試繞過網路安全措施以存取敏感資料。當 IPS 檢測到這些連接嘗試時，它將自動阻止該連接，保護網路的完整性和安全性。

這些實例展示了入侵防禦系統 (IPS) 如何在不同情況下主動保護網路和資源免受攻擊。

[return to content](#000) 

<a name="222"/>

## 實戰2: 設置防火牆 (Setting Up Your Firewall) 

### 1. Win10: 請檢查您的防火牆設定，並確認目前設定是否開啟?並確認開啟下的設定的細節.

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/21b09708-7036-447f-a1f7-9dc5bf34f825)

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/808422a6-9066-4239-ab45-63e8b555c1b5)

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/0bb84ef2-715a-4ce8-bef1-f3f0568ab1d3)

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/e240f0a6-6cc7-4431-ad3b-629ef837541f)

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/d829a437-b378-4b59-9160-920faa0daedf)


### Linux Ubuntu: 如何安裝防火牆並檢查狀態?

![image](https://github.com/Grace-TA/CyberSecurity-Spring2023/assets/89304181/8a468eef-56bb-483d-92b2-e9fcc74bdcf7)

[return to content](#000) 

