# 六、網路與通訊安全：@網路安全、@通訊安全
# 1. 針對網路各層的攻擊手法：
```
實體層—線路搭接與線路私接
資料連結層—封包監聽與ARP Spoofing
網路層—Source Route、Smurf、Ping of Death 
連線層—SYN Flood、DDoS及Session Hijacking
應用層—DNS Poisoning、Brute force Login、SQL Injection及Cross-Site Scripting
```
# A.實體層
```
>>> 攻擊方式：
搭接線路(網路與電話)進行訊號竊聽、私接線路變成隱匿通道(非控管中的線路)
>>> 防護建議：
機房、機櫃、線路室及管道間進行存取控管、採用不同顏色區隔不同網段(安全區域)、定期的線路盤查
```
# B.資料連結層_封包監聽
```
透過工具或軟體被動蒐集Collision Domain中的網路封包
>>> 監聽工具：
>* Sniffer, MailSnarf
>* URLSnarf, WebSpy
>* Tcpdump ,Windump
>* Wireshark(Ethereal)
>* Ettercap
>>> 防護建議：
>* 採用加密連線(最佳方法)
>* 改用Switch
>* 網路線路的實體存取控制，避免搭接或私接問題
```
# B.資料連結層_ARP Spoofing
```
ARP(Address Resolution Protocol)用來對應MAC與IP位址的協定
又稱為ARP flooding、ARP poisoning或ARP Poison Routing
在Broadcast Domain下無法被動監聽其他電腦間連線封包
ARP Spoofing攻擊強迫偽冒其他IP，讓攻擊者有機會監測到其他電腦間的通訊
>>> 攻擊手法：
攻擊者使用ARP Broadcast封包告訴其他電腦，192.168.1.1的MAC是Attacker的MAC
其他電腦要傳送給192.168.1.1的封包會被送到Attacker
Attacker將封包錄下後轉送到真正的192.168.1.1
>>> 防護建議：
強制使用靜態ARP Table(小型網路)
採用VLAN縮小Broadcast Domain的範圍
啟用Switch中的Port、MAC及IP的對應控管
```
# C.網路層_Source Route
```
IP封包的路由通常是由Router所決定，啟用Source Route可以讓傳送者指定IP封包的傳送路徑
攻擊者運用Source Route的功能進行來源IP的偽冒(IP Spoofing)
讓偽冒來源IP的封包可照指定路徑送到目的伺服器、FW信任偽冒的來源IP未加以阻擋
防護建議：在防火牆或路由器上阻擋採用Source Route的封包
```
# IP Spoofing與ARP Spoofing
```
IP Spoofing使用偽造的來源位址來傳送IP封包，可能會採用受信任來源的IP 位址來嘗試規避防火牆
ARP Spoofing是指攻擊者取得區域網路上的資料封包甚至篡改封包，可讓網路上特定電腦或所有電腦無法正常連線
```
# C.網路層_Smurf Attack：藉由ICMP封包塞爆受害者網路頻寬的阻斷服務攻擊
```
>>> 攻擊手法：
攻擊者(Attacker)偽冒受害者IP(Victim)發送大量Echo Request給B網段的Broadcast IP位址(B.255或B.0)
B網段所有電腦收到Echo Request封包，都回覆Echo Reply封包給Victim
導致Victim端頻寬被大量的Echo Reply封包所占用
>>> 防護建議：
在防火牆或路由器上阻擋Network/Broadcast IP的傳送
```
# C.網路層_Ping of Death：屬於一種阻斷服務攻擊，只要一個Ping封包就讓作業系統當機
```
>>> 攻擊手法：
一般正常的Ping封包大小為56位元(含IP標頭為84位元)
攻擊者故意傳送一個大小超過65536位元的Ping封包給受害者(IP協定允許封包大於65536)
受害作業系統無法處理大於65536位元的Ping封包，導致系統當機或重新開機
攻擊者的來源IP經常是偽冒的IP位址
>>> 防護建議：
修補作業系統弱點(目前大部份作業系統都已修補這個弱點)
```
# D.連線層_SYN Flood
```
>>>　攻擊手法：
攻擊者傳送大量的TCP SYN請求封包到受害伺服器
受害伺服器為每一個連線請求分配系統記憶體資源，導致系統連線資源被耗用殆盡，正常的連線無法建立
大量惡意的TCP SYN封包，其來源IP通常也都是偽冒的，因此無法以封鎖來源IP阻擋攻擊
>>> 防護建議：
防火牆限制同來源IP的連線數量
請求ISP協助
```
# D.連線層_分散式阻斷服務攻擊：(Distributed Denial-of-Service，簡稱DDoS)
```
>>> 攻擊手法：
攻擊者控制多部阻斷服務攻擊主機(DoS Agent)，對受害者發動大規模的阻斷服務攻擊
被攻擊的受害者為主要受害者，被控制的阻斷服務攻擊主機本身也是次要的受害者
其攻擊來源IP太多(數百至數千個)，通常很難透過防火牆封鎖來源IP
>>>　防護建議：
防火牆限制同一來源IP的連線數量
請求ISP協助
>>>　案例：
巴哈姆特遭大陸駭客DDoS攻擊
```
# D.連線層_Session Hijacking
```
>>> 可分為兩種類型：
主動型：攻擊者取代已建立之有效的連線
被動型：攻擊者攔截連線後只監聽連線內容
>>> 攻擊的步驟：
追蹤連線過程
連線去同步化
注入攻擊者的封包
>>> 防護建議：
採用IPSec或SSL雙向認證的加密連線
當攻擊者可以預測到Client下一個封包的序號時，就可以偽冒Client的IP送出封包給Server，達到攔截連線的攻擊
```
# E.應用層_DNS Poisoning
```
攻擊者藉由DNS伺服器的弱點，將錯誤的名稱解析植入DNS伺服器的快取區(Cache)中，導致DNS用戶端解析到錯誤的IP，使網路連線被導到惡意的伺服器
>>> 防護建議：
修補已知的DNS伺服器弱點
區隔外部與內部DNS伺服器(不要forward到ISP的DNS)
```
# E.應用層_Brute force Login
```
>>> 攻擊者透過通行碼猜測入侵應用系統的狀況相當常見，例如：
TELNET login
SSH login
FTP login
SMTP AUTH
POP3 login
>>>　網路上有相當多的工具可自動進行通行碼猜測攻擊：
Brutus
THC-Hydra
>>> 防護建議：
限制同一帳戶連續簽入失敗之次數，若超過次數則延遲簽入一段時間或關閉帳號，發出警告訊息
強制使用者通行碼長度與複雜度
定期更換通行碼
```
# E.應用層_SQL Injection
```
>>> 簡介：
攻擊者可以將惡意之SQL指令插入程式碼的SQL指令中
Blind SQL Injection：SQL指令注入後只回傳某些狀態，無法得知資料內容
SQL指令注入的弱點發生在Web應用程式中，但受到損害的卻是其後端的資料庫
>>> 可能的損壞：
資料庫之資料外洩、資料庫內容被修改、執行資料庫管理、網站權限跳脫或植入後門程式
>>> 弱點原理：
Web應用程式將「不可信任來源」的資訊直接組合成SQL指令後執行，就會產生SQL指令注入弱點
>>> 防護建議：
網站應用程式源碼檢測與資料輸出至資料庫前過濾SQL指令使用之特殊符號(例如：單引號與分號等)或採參數化查詢語句
```
# E.應用層_Cross-Site Scripting
```
>>> 簡介：
簡稱XSS
攻擊者可透過XSS弱點將惡意腳本(例如：JavaScript與VBScript)置入Web伺服器
當其他使用者瀏覽到被置入惡意腳本的網頁時，使其瀏覽器執行惡意腳本
可區分為儲存型(Stored XSS)與反應型(Reflected XSS)兩類
>>> 可能的損壞：
機密資訊被竊取(例如：Cookie與Session ID等)
下載後門程式植入偽冒資訊
>>> 弱點原理：
Web應用程式將「不可信任來源」的資訊直接輸出至網頁或其他輸出標的就會產生XSS弱點
>>> 防護建議：
網站應用程式源碼檢測與資料輸出時做HTML特殊符號的過濾
```
# 2.從SWIFT通訊系統來看網路安全：
>* 遠東銀行SWIFT遭駭事件是臺灣首例，創下臺灣銀行遭駭盜轉金額新紀錄
>* 全球金融機構通用的SWIFT通訊系統是銀行間交易中交換結構化的電子訊息的平臺，處理支付和交易結算等商業流程
>* 駭客利用SWIFT系統的漏洞，或網路進行攻擊，來取得SWIFT系統的操作權限，植入惡意程式，將該銀行的資金轉出
>* SWIFT要求會員銀行遵守多項強制控制措施，並自2018年起對會員銀行進行稽核
