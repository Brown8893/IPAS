# 六、網路與通訊安全：@網路安全、@通訊安全
# 1. 針對網路各層的攻擊手法：
```
實體層—線路搭接與線路私接
資料連結層—封包監聽與ARP Spoofing
網路層—Source Route、Smurf、Ping of Death 
連線層—SYN Flood、DDoS及Session Hijacking
應用層—DNS Poisoning、Brute force Login、SQL Injection及Cross-Site Scripting
```
```
A.實體層
```
>* 攻擊方式：
>* 搭接線路(網路與電話)進行訊號竊聽、私接線路變成隱匿通道(非控管中的線路)
>* 防護建議：
>* 機房、機櫃、線路室及管道間進行存取控管、採用不同顏色區隔不同網段(安全區域)、定期的線路盤查
```
B.資料連結層_封包監聽
```
>* 透過工具或軟體被動蒐集Collision Domain中的網路封包
>* 監聽工具：
>* Sniffer, MailSnarf
>* URLSnarf, WebSpy
>* Tcpdump ,Windump
>* Wireshark(Ethereal)
>* Ettercap
>* NetIntercept
>* 防護建議：
>* 採用加密連線(最佳方法)
>* 改用Switch
>* 網路線路的實體存取控制，避免搭接或私接問題
```
B.資料連結層_ARP Spoofing
```
>* ARP(Address Resolution Protocol)用來對應MAC與IP位址的協定
>* 又稱為ARP flooding、ARP poisoning或ARP Poison Routing
>* 在Broadcast Domain下無法被動監聽其他電腦間連線封包
>* ARP Spoofing攻擊強迫偽冒其他IP，讓攻擊者有機會監測到其他電腦間的通訊
>* 攻擊手法：
>* 攻擊者使用ARP Broadcast封包告訴其他電腦，192.168.1.1的MAC是Attacker的MAC
>* 其他電腦要傳送給192.168.1.1的封包會被送到Attacker
>* Attacker將封包錄下後轉送到真正的192.168.1.1
>* 防護建議：
>* 強制使用靜態ARP Table(小型網路)
>* 採用VLAN縮小Broadcast Domain的範圍
>* 啟用Switch中的Port、MAC及IP的對應控管
```
C.網路層_Source Route
```
>* IP封包的路由通常是由Router所決定，啟用Source Route可以讓傳送者指定IP封包的傳送路徑
>* 攻擊者運用Source Route的功能進行來源IP的偽冒(IP Spoofing)
>* 讓偽冒來源IP的封包可照指定路徑送到目的伺服器、FW信任偽冒的來源IP未加以阻擋
>* 防護建議：在防火牆或路由器上阻擋採用Source Route的封包
# IP Spoofing與ARP Spoofing
```
IP Spoofing使用偽造的來源位址來傳送IP封包，可能會採用受信任來源的IP 位址來嘗試規避防火牆
ARP Spoofing是指攻擊者取得區域網路上的資料封包甚至篡改封包，可讓網路上特定電腦或所有電腦無法正常連線
```
```
C.網路層_Smurf Attack：藉由ICMP封包塞爆受害者網路頻寬的阻斷服務攻擊
```
>* 攻擊手法：
>* 攻擊者(Attacker)偽冒受害者IP(Victim)發送大量Echo Request給B網段的Broadcast IP位址(B.255或B.0)
>* B網段所有電腦收到Echo Request封包，都回覆Echo Reply封包給Victim
>* 導致Victim端頻寬被大量的Echo Reply封包所占用
>* 防護建議：
>* 在防火牆或路由器上阻擋Network/Broadcast IP的傳送
```
C.網路層_Ping of Death：屬於一種阻斷服務攻擊，只要一個Ping封包就讓作業系統當機
```
