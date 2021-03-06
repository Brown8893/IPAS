# 四、事故管理與營運持續：@事件與事故管理、@備援與營運持續

# 1.重要字詞與定義：
```
事件、事故、通報流程、升級(功能與階層)、暫時解決方案、衝擊、優先處理順序、緊急處理
```
# 2.資安事故處理的目的：
>* 確認資安事故是否發生
>* 降低對業務與網路服務的中斷時間
>* 提供精準與即時的資訊
>* 保障由政策與法律要求的權利
>* 實作控制措施以維護監管鏈
>* 讓法務組織可對惡意者提起訴訟
# 3.有效的資安事故處理計畫：
```
>定期重新審查計畫文件：
-更新人員、科技及業務處理流程
>訓練：
-組織分工與權責、資訊安全技能、危機處理、數位鑑識與調查技能及溝通能力
>財務支持：
-預算、額外的設備、專業人員、員工薪資及訓練費用
>演練：
-定期驗證與修正作業流程
```
# 4.資安事故處理程序：
## A.程序：
```
準備>識別>封鎖>根除>回復>經驗學習
```
## B.準備：
>* 1)資安事故成功處理的關鍵是事前的「準備」
```
a.組織資安事故處理小組
b.建立資安事故處理策略
c.設計資安事故處理程序
d.建立溝通管道與方式
e.蒐集所需資源
f.練習、練習、再練習
```
>* 2)資安事故處理小組
```
技術部門(IT、資訊安全及系統管理者)
管理人員
法務部門
數位鑑識專家
公共關係部門
人力資源部門
實體安全與維護部門
通訊部門
```
## C.識別：
```
a.資安事故無法完全防制，但必須被偵測
b.識別意圖(故意或無意)
c.確認範圍
-識別哪些系統、人員及資訊資產被包含在處理的資安事故中
d.保留證據 
-保護資安事故的事實
e.可疑的事故
-新增帳號、新建檔案及檔案的修改
-入侵偵測系統觸發的事件與防火牆存取紀錄
-效能變差、服務無回應及系統不穩定
f.監聽正在進行的攻擊行為
-透過網路封包的蒐集
g.數位證據的取得
-採用被接受的磁碟映像複製工具(所有磁區的複製，配合雜湊函數以檢驗被複製出來的資料沒有被竄改)
-配合錄影機記錄螢幕顯示的內容與採證過程
h.識別出來的相關證物從發現到提出至法院必須有完整明確的監管紀錄
-每一項證據必須由可證明身分的人員所保管
-當保管人交接時必須被記錄
-在儲存體中的證物必須被保護，以免被污染或變更
```
## D.封鎖：
```
a.當資安事故已被識別且相關證物監管鏈已被建立後，接下來就開始「封鎖」入侵來源，以避免災害擴大
b.識別可信任來源
-不只是來源網路地址或設備，也包含使用者
c.避免驚動入侵者以避免證據被銷毀
d.開始進行證據分析與數位鑑識
e.減緩攻擊的封鎖行動
-變更通行碼與權限
-變更主機名稱與IP位址
-將可疑的流量導到不存在的位址
-阻擋攻擊來源IP或網段
-在類似系統上更新修補程式
-關閉服務
```
## E.根除：
```
a.一旦資安事故已被控制，接下來要從系統或網路中完全移除惡意程式
b.決定採用移除或回存方式
-是否可以完全移除乾淨
-備份資料中可能就存有惡意程式
c.強化防禦機制
-建立額外的偵測與防禦方法
-提升稽核紀錄的詳細程度
-在其他系統中尋找已發現的惡意程式
-更嚴謹控管存取來源
```
## F.復原
```
a.一旦威脅被根除，接下來應開始將業務與服務回復至正常運作狀態
b.加強監控以偵測攻擊是否再發生
-客製化入侵偵測規則
-在網路、主機及應用程式中，實作額外更詳細的稽核紀錄
```
## G.經驗學習
```
a.開經驗學習會議
-在相關處理人員記憶猶新的情況下
-讓組織在資安事故中學習防護經驗
-建議修改相關政策或程序，以利未來安全防護機制實作時可避免重蹈覆轍
```

# 5.業務永續運作計畫之目的
```
>防止業務活動中斷，確保重要關鍵業務流程不受重大故障與災難的影響
>結合預防與復原措施，將風險造成的影響降低到可以接受的等級
>分析災難、安全缺失及服務損失的後果。制定與實施應變計畫，確保在要求的時間內恢復業務流程
>選用控制措施降低風險，限制破壞性事件造成的後果，確保重要作業能及時復原
```
## ※ 業務永續管理的發展沿革
```
備援計畫(備援計畫)
↓
災害復原計畫(DRP)(IT或技術性的持續運作計畫)
↓
業務永續計畫(BCP)(組織範圍的業務永續計畫)
↓
業務永續運作管理(BCM)(完整的業務永續計畫)
```
# 6.業務永續運作管理程序：
```
業務永續運作的需求>營運衝擊分析>識別防禦性控制措施>發展復原策略>發展業務永續運作計畫>測試與演練>維護業務永續運作計畫
```
>* 必須獲得高階管理人員「認同與支持」，必須是關鍵業務所有相關部門投入，並非是資訊部門的責任
# 7.業務永續運作的需求：
```
>法律與規範的要求
>定義範圍：
-BCP需要處理的災害類型：天災與人禍
-全部、特定區域及特定業務
>參與角色：
-計畫主要負責人
-各部門主管與高階管理人
-IT部門、安全部門及通訊部門
-法務部門
-當災害發生時需要執行BCP計畫的部門都應參與BCP的發展
```
# 8.營運衝擊分析(Business Impact Analysis,BIA)：
```
>用來瞭解當災害發生後的嚴重程度，以及需要多少時間來處理
>BIA的步驟：
-識別組織的關鍵業務功能
-識別關鍵業務所仰賴的資源
-計算關鍵業務可容許缺少資源的時間
-識別關鍵業務面臨的威脅與弱點
-計算不同業務功能的風險
-確認業務功能與資源復原的先後順序
```
```
>營運衝擊分析：
-資訊業務營運持續計畫因應外在或內部作業環境之變化，每年至少進行乙次測試及檢討
>進行營運衝擊分析時，應就下列項目進行評估：
-進行關鍵營運業務之辨識
-各營運活動可容忍中斷之時間(Recovery Time Objective, RTO)
-各營運活動可容忍資料遺失之期間(Recovery Point Objective, RPO)
-組織可容許的資訊安全水準(如：安控防護程度、權限控管、加密強度等要求)
-於作業復原時所需之資源及預算
-就衝擊分析之結果，考慮成本效益因素，進行因應方案之可行性分析，再根據評估結果，評估建置適當之備援機制，並制訂資訊業務營運持續計畫
```
# 9.發展復原策略
```
>目的：
-指導復原作業的規劃方式與規模(成本)
>參考：
-關鍵業務最大容許中斷時間
>必須包含下列復原策略：
-業務流程復原策略
-設施場所復原策略
-供應與技術復原策略
-使用者環境復原策略
-資料復原策略
>業務流程復原策略：
-其他業務處理流程(自動 vs 人工)
-業務處理流程重建
```
```
>>設施場所復原策略：
-Hot(數小時)、Warm(1天或更長)或Cold(數天) Site合約
-同業互惠合作、自建備援場所及自建分散式多重處理機制
-備援場所應有足夠合理的距離(避免同一災害同時受損)
```
```
>供應與技術復原：
-網路與電腦設備
-語音與資料通訊
-人力資源
-人員與設備的運送
-作業環境(空調等)
-資料與人員安全
-耗材
-文件
>使用者環境復原：
-發展災害情況下的通報網
-識別關鍵使用者以利關鍵業務的運作
-必要時發展人員運送至備援場所的程序
```
```
>資料復原：
-備份
-異地備份
-異地備援
>其他注意事項：
-備援與復原機制的選擇應考量成本效益
-備份與備援機制的安全要求應與線上相同
-備份與備援機制應定期測試與演練
```
# 10.發展業務永續運作計畫
```
>復原階段：
-主要目的是讓關鍵業務回復至暫時可運作的狀態
-復原程序應包含系統回復至可運作狀態的每一步動作，而且必須在可容許中斷的時間內完成
```
```
>重建階段：
-主要目的是讓關鍵業務從暫時運作狀態，在原地點或其他地點回復到一般正常作業
-在重組後的新環境應執行相關系統與作業測試
-由較不重要的業務功能先移轉至新環境
```
# 11.測試與演練
```
>目的：
-檢驗BCP的可行性並補強未考量之缺陷
-確保在可容許中斷時間內可完成復原作業
-讓相關人員熟悉相關災害復原的作業
>測試方式：
-檢核表測試(部門個別檢視BCP工作)
**無法得知不同部門間的合作與溝通結果
-整合測試(各部門一起檢視BCP過程)
**無法模擬不同的災害類型或損壞情況來應變
-狀況模擬測試(紙上模擬災害情境與復原過程)
**缺乏實際執行復原與重建的經驗
```
```
>測試方式：
-並行測試(實際將部份系統及業務移轉到備援場所，但原場所仍持續運作，可實際測試是否能在最大容許中斷時間內復原) ，可能導致部份業務無法運作
-完全中斷測試(中斷原場所系統及服務，實際摸擬BCP的復原階段與重建階段)
**關鍵業務必須中斷一段時間
**部份業務可能無法及時復原運作
**重建階段演練時，資料若需回存到原系統，可能導致資料錯亂
>測試與演練的時機：
-定期(每年)
-BCP有重大變更時可額外進行
```
```
>在測試與演練中學習：
-測試結果與經驗應被記錄
-彙整測試結果並於測試後進行檢討，以改善現有BCP的缺失
```
## ※ 維護業務永續運作計畫
```
>目的：
-確保BCP可符合組織現況需求
>CP會因下列因素變成不符現況需求：
-科技的快速變動或軟體升級
-組織組織變更(分工方式、合併或裁減)
-人員異動
>如何確保BCP可符合現況：
-指派專責人員或部門負責持續更新
-將計畫的審查加入組織定期稽核項目
-在變更控制程序中審查是否需要更新BCP
```
## ※ 如何判斷BCP是正確且有效的？
>* 在可容許中斷時間內可以復原
>* 在暫時備援環境中的作業是適當可行的
>* 備份資料可被成功回存
>* 緊急處理人員、服務人員及合約要求人員在可接受的時間內可以到達
>* 小組成員瞭解現有BCP內容
>* 小組成員可執行BCP的職責
>* BCP與現況需求符合
# 12.重要字詞與定義：
>* 營運衝擊分析(BIA)
>* RPO- Recovery Point Objective
>* 備份(Full Diff. Incr.)
>* 風險評鑑
>* 備援中心(冷、暖、熱、鏡)
>* RTO- Recovery Time Objective
>* 營運持續策略
>* 營運持續計畫(BCP)
>* MTPD-Max. Tolerable Period of Disruption
