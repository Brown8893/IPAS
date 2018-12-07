# 七、作業系統與應用程式安全：@作業系統安全、@作業系統與應用程式(含資料庫與網頁)攻擊手法、@程式與開發安全

# 1.應用程式安全問題的基本觀念
```
>>> 軟體安全工程(software security engineering)探討軟體安全問題的解決方法：
-應用安全屬於軟體工程的問題，由設計來解決
-架構安全屬於系統管理問題，由設定來解決
>>> 安全要求高的軟體，需要特別訂定安全性規格(safety specification)：
-從實際應用的角度來評估風險
-依實際的需求來設計軟體系統降低風險與損害
```
# 2.應用程式的威脅
>* 緩衝區溢位(Buffer overflow)
>* 惡意程式碼(Malware)
>* 輸入攻擊
>* 後門程式
>* 邏輯炸彈
>* 行動應用(app)的攻擊
>* 社交軟體的攻擊
# 3.緩衝區溢位(Buffer overflow)
>* 緩衝區是程式執行期間在記憶體中用來存放資料的空間
>* 當應用程式處理資料時未檢查輸入資料的長度，就有可能讓太長的資料覆蓋到其他記憶體區段，導致惡意程式碼被植入且被執行
# 4.惡意程式碼
>* 惡意程式碼可分為病毒、蠕蟲、後門、木馬及間諜程式
>* 這些惡意程式碼可能會附著在應用程式中，也可能獨立存在，導致程式執行效能變差與資料被竊
>* 病毒
```
需被動依賴寄宿的應用程式重製自已或感染其他程式
```
>* 蠕蟲
```
自己有能力主動進行傳染散播的惡意程式
```
>* 後門
```
留在系統內不需經一般安全控管程序，就可以被植入者遙控的惡意程式
```
>* 木馬
```
是一個陷阱程式，等待使用者踩到陷阱程式後，運用使用者權限執行不當的指令
```
## ※ 惡意程式碼
```
>>> 間諜程式：
-主要以竊取系統的機密資料為主的程式、例如：上網行為與鍵盤側錄等
>>> 現今的惡意程式不見得只單純扮演一種角色，可結合各種不同的手法與行為感染與散播：
-例如：USB病毒在USB硬碟時，運用病毒被動感染的方式感染電腦主機，一旦感染電腦主機後可能變成主動感染其他系統的蠕蟲
```
# 5.後門程式
```
>>> 留在系統內不需經一般安全控管程序，就可以被植入者遙控的惡意程式
>>> 維護用後門程式：
-開發人員私下留存在應用程式內，以方便日後
>>> 進行維護的程式：
-應用程式於整合測試階段，應檢查應用程式中是否含有後門程式
>>> 被惡意植入的後門程式：
-由於應用程式其他的弱點(如：Command Injection)，導致惡意後門程式被植入應用系統中
-應用程式清單應被妥善維護，以區別非授權程式，也可以善用檔案的完整性檢查工具
```
# 6.邏輯炸彈
```
>>>　邏輯炸彈是一段被故意插入應用程式的程式片段，在正常情況下並不會被執行。只有當特定條件符合時才會被啟動：
-例如：程式設計師隱藏了一段刪除薪資資料庫的程式碼，只有當他被解僱的條件符合時才會被執行
>>> 有些病毒與蠕蟲也會具有邏輯炸彈的程式碼：
-例如：當4月1日愚人節時將硬碟刪除
>>>　應用程式於整合測試階段，應檢查應用程式中是否含有邏輯炸彈
```
# 7.駭客手法演變
```
>>> Web 1.0 (1990 至 2000)
-駭客為了知名度**網頁置換
>>> Pre-Web 2.0  (2000 至 2004)
-駭客為了控制網頁伺服器**用戶資料庫、信用卡號碼及交易紀錄
-對個人電腦沒興趣
>>> Web 2.0 (2004 至 2009)
-人人是高度網路化的世界公民，從電腦可找出生活足跡
-駭客對於個人電腦更有興趣
>>> 擴展到行動載具與社交軟體的攻擊
```
# 8.OWASP Top 10 2017
>* A1 Injection
>* A2 Broken Authentication and Session Management
>* A3 Sensitive Data Exposure 
>* A4 XML External Entities (XXE) (NEW)
>* A5 Broken Access Control
>* A6 Security Misconfiguration 
>* A7 Cross-Site Scripting (XSS) 
>* A8 Insecure Deserialization (New)
>* A9 Using Components with Known Vulnerabilities
>* A10 Insufficient Logging & Monitoring (New)
# 9.使用SSL就可以確保網站安全?
```
>>> 經常聽到對於 SSL 的錯誤解讀：
-網站使用 SSL加密，不怕資料外洩
-我們的 SSL 用了 強固式加密，所以很安全
>>> 事實上，使用SSL並不等於作好網站應用程式安全：
-SSL 僅限傳輸過程的私密性保護，並不代表資料儲存時的私密保護
-網站應用程式安全與資料傳輸的安全，為不同領域的問題
-資料加密的連線內容，防火牆/IDS/IPS是看不懂的！
-無法避免當駭客偽裝成使用者時在SSL連線中進行攻擊
```
# 10.已上線網站應用程式安全的防護
```
>>> 定期針對作業系統、網站伺服器及資料庫伺服器執行弱點掃描與修補
>>> 定期執行網站應用程式弱點掃描：
-黑箱檢測工具(模擬SQL Injection、XSS等攻擊)
-白箱檢測工具(靜態分析應用程式原始碼)
-滲透測試(權限跳脫與邏輯錯誤)
>>> 有能力修改程式：
-修補已發現的應用程式弱點
>>> 無能力修改程式：
-建置Web應用程式防火牆進行弱點防禦
>>> 新開發的應用程式請參考「安全軟體開發生命週期(SSDLC)」
```
## ※ Web應用程式安全檢測方法(參考Day2_NEW p.75)
# 11.變更控制
```
>>> 原因：
-應用程式上線後因需求的變更、新功能要求及發現新瑕疵等因素，需要變更應用系統程式或組態
>>> 目的：
-為維持變更後的安全狀態仍可符合安全政策要求
>>> 方法：
-組織應實作應用程式變更控制流程
-必須確保變更是獲得授權、經過測試且被記錄下來的
```
```
>>> 變更控制流程必要的步驟：
-填寫變更需求申請
-分析變更需求
-發展實作策略、方法或步驟
-計算變更所需成本
-評估變更與安全的關聯性
-記錄變更請求
-提交變更申請進行核准
-進行應用程式變更的開發工作
-記錄變更開發的產出(新增或刪除功能)
-將變更的程式碼與變更申請連結(程式碼中的註解)
-將變更後的程式碼交付測試與品質認可
-變更程式碼版本(上線)
-向管理階層報告變更結果
```
# 12.職責區隔
>* 作業人員不應有權限存取線上的程式碼或程式物件
>* 程式設計人員不應存取線上運作中的軟體
>* 品管部門應測試程式碼品質，且與開發部門採用不同的測試方法
>* 一旦軟體被開發測試完成應被保存在程式庫中
>* 線上運作的軟體應由程式庫中發行，不應直接由程式設計人員或測試人員進行更新
# 13.程式庫維護
>* 應用程式應集中存放在程式庫中，並進行存取控管
>* 程式庫進行版本控制，並保留所有版本程式碼
```
主版本：1.0
次版本：1.1
緊急修正版本：1.0.1
```
>* 開發部門凍結版本後應簽入(Check In)到程式庫，也應由程式庫中簽出(Check Out)取得最新版本進行修改
>* 測試部門應由程式庫中簽出(Check Out)取得最新版本進行測試
>* 上線人員應由程式庫中發行(Release)最新版本應用程式至線上系統
# 14.應用程式的品質與安全檢測
>* 任何應用程式都有可能有瑕疵或是弱點
```
安全程式開發(secure programming)是直接嘗試消除程式瑕疵
安全檢測則是嘗試在有瑕疵的程式存在的情況下保護系統資源不受危害
```
>* 使用者、程式設計者與系統管理員對於程式安全的認知是不同的
>* 技術上可依病毒的特性對程式進行檢測
>* 通常需要工具的輔助
## ※ 行動應用(app)的安全問題
>* 行動應用(app)也是應用程式的一類
>* 駭客可以循傳統的技術進行病毒的感染
>* 駭客也可以運用反向工程的技術來變造原來的程式，將變造以後的app送上程式商店引誘使用者下載
>* 行動應用(app)的資安問題持續攀升
>* 開發行動應用(app)時需注意採用的套件的安全
>* app開發時，索取過多行動裝置上的敏感資訊，例如：通訊錄、行事曆、座標位置、郵件、簡訊內容等，易侵犯隱私
# 15.安全軟體開發生命週期簡介
>* 安全的軟體開發生命週期(Secure Software Development Life Cycle, SSDLC)意指發展一套安全的軟體之順序，主要可分為：
```
需求分析(Requirements)：風險評估、資安要求
↓
架構設計(Design)：威脅模型、資安架構
↓
程式實作(Implementation)：安全源碼撰寫
↓
測試與驗收(Testing)：品質確保、系統驗收
↓
部署、運作與維護(Maintenance)：教育訓練、修補與更版、即時監控
```
```
>>> 需求分析(Requirements)：
著重資安需求定義，以符合使用者需求與法規遵循為目的
>>> 架構設計(Design)：
根據需求分析結果，進行包含系統任務的目標、功能關聯、邊界範圍及各階層使用者的角色等內外部使用的規劃與搭配適當的資安架構
>>> 程式實作(Implementation)：
落實既有之規劃，將使用者介面、功能運作及安全性等完整的實現
```
```
>>> 測試與驗收(Testing)：
-進行運作模擬，檢驗該系統的完成度，確保各項功能與安全性皆可符合既定的需求
>>> 部署與維運(Maintenance)：
-進行軟體之部署，安排教育訓練
-落實軟體之穩定運作，應定期修補漏洞(Patch)、按步升級更新版本(Upgrade)及即時監控(Monitor)
```
# 16.計畫作業階段
```
>>> 委外可行性分析：
篩選適合委託辦理之業務項目
進行成本效益分析
>>> 資訊風險評估：
深入瞭解委外服務面臨的資安風險
>>> 規劃作業：
-專案編成(蒐集內部資安需求)
-廠商提出對應措施方案(RFI或RFC蒐集外部資安需求)
-安全需求項目規劃
**徵求建議書文件(清楚描述資安需求與廠商之資安責任)
**委外契約書(相關法定資安責任必須由廠商共同承擔)
**服務水準協定(明訂可量測之服務水準)
-組織採購資訊安全考量(不友善國家之資金、服務及產品)
```
# 17.招標階段
```
>>> 依循組織採購法所規範之項目外，應著重於下列各項因素：
-評選委員學經歷
-著作要求
-相關領域實務經驗
-利益迴避限制條件
```
# 18.決標階段
```
>>> 決標階段之重點為與廠商之簽約作業
>>> 簽約行為重點：
-查核廠商是否完成保密切結
-完成專案編組
```
# 19.履約管理階段
```
>>> 資訊安全組織：
-組織與委外廠商皆應指定專案管理人員，負責推動、協調及督導資訊安全管理事項
>>> 委外相關風險識別：
-組織經由委外作業過程產生對組織資訊與資訊處理設施之風險，宜在核准廠商存取內部設施之前加以識別，並實作適當的控制措施
>>> 與廠商協議中之安全說明：
-所有因委外作業衍生對應之內部控制措施的安全要求，宜反映在與委外廠商的協議中
>>> 委外人力資源安全(僱用前、期間、終止或變更)：
-資訊作業委外前宜依適當的工作職掌，並依契約條款與條件闡明廠商應負之安全責任，並進行充分適當的篩選
```
```
>>> 委外實體與環境安全：
-防止組織場所內資訊因委外作業而遭未經授權的實體存取、損害及干擾，關鍵或敏感的資訊處理設施宜置放於安全區域
>>> 委外之作業管理：
-委外相關作業應符合組織安全政策與程序之要求
>>> 委外使用者存取管理：
-組織宜有正式程序，以控制資訊系統與服務的存取權限配置作業
>>> 委外資訊安全事故管理：
-委外組織宜備妥正式的事故通報與提報程序，提供委外作業廠商配合並施予合宜訓練
>>> 遵循適法性要求：
-組織於資訊系統設計、運作、使用及管理都應受法律、法令、法規或契約的安全要求所規範，所參照之規範宜明確界定、文件化及維持最新版本
```
# 20.驗收階段
>* 組織執行「驗收階段」程序，係依據契約文件與「履約管理」階段執行成果辦理
>* 以「專案工作計畫書」內容確認委外專案之進行方式、專案組織、相關時程及資訊安全要求事項是否符合
>* 而委外廠商也須將定期召開工作進度報告會議之內容，如應完成重要工作項目、已完成工作的項目、預計工作項目、問題與建議等，提供驗收單位佐證
# 21.爭議處理
```
>>> 組織與廠商因履約管理產生爭議未能達成協議者，得以下列方式之一處理： 
-向採購申訴審議委員會申請調解
-向仲裁機構提付仲裁
>>> 然若雙方於問題標準界定上有所爭議時
-可蒐集發生的事證與相關資訊
-尋求具公信力之第三者、學者專家、法院或調解委員會(如行政院公共工程委員會)等
-進行問題的釐清與相關問題的調解
```
# 22.重要字辭與定義
>* 木馬
>* DDoS
>* 病毒/蠕蟲
>* 可移動式設備
>* 防毒
>* 社交工程
>* 密碼強度
>* 修補程式
>* 登入安全管控 (錯誤訊息)
>* 特權工具
>* 驗證碼
>* WSUS/ Antivirus
>* 最低權限
>* 資料庫稽核
>* 勒索軟體 (對策)
>* 網頁安全/監控(置換)
>* 網頁攻擊手法 (SQL Injection, XSS…)
>* WAF
>* 網頁安全/監控(置換)
>* … 各種主機攻擊手法特性 (Protocol)
>* 委外開發合約
>* 委外開發安全要求
>* 測試與驗收
>* 原碼檢測
>* 開發生命週期安全
>* 上線安全
>* Code review
>* 安全規格分析
>* Roll back plan