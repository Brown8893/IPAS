# 一、資訊安全管理概念：@機密性.完整性.可用性定義、@資訊安全管理系統
# 1.IPX BSF ZPV -1 （答：HOW ARE YOU）
# 2.重要字辭與定義：
>* A.
機密性（隱私保密.不上讀.不下寫）、可用性（被授權的時間讀它可用的東西）、完整性（完全+正確.不上寫.不下讀）、鑑別度（要知道它是誰）、不可否認性（你有做過不能否認沒做過）、可靠度、可歸責性（事件發生後責任歸咎）
*機密&完整>衝突
*請問備份是保護機密？完整？還是可用？>可用性
>* B.
ISO 27001/ISMS、風險管理（取得平衡）、控制項、政策（最大的方向）、PDCA（Plan Do Check Act.戴明循環）、教育訓練/意識、量測/績效、矯正措施、有效性
*風險管理：PTT 帳密沒加密，為「撞庫」、銀行帳戶分散存款、取得平衡
# 3.重要資安概念：
>* 1）邊界與分類（Boundary and classification）
>* 2）職務區隔（Segregation of duties, SOD）>密碼分開輸入
>* 3）縱深防禦（Layered defense, defense in depth）>很多種管控
>* 4）單一脆弱點（Single point of failure, SPOF）>設備買一台壞掉即無用
>* 5）阿奇里斯腱（Achilles heel）>安全強度永遠等於最弱點
>* 6）木桶理論（Bucker principle）
>* 7）僅知原則（Need to know）>業務需知
## 資安最弱點是"人"
## 社交工程>>郵件勿亂點
# 4.安全（Security）：機密性+可靠度+完整性
# 5.資訊安全的三個目標：
>* 機密性(Confidentiality)：資訊之「秘密性」&「隱私性」，防止機密資訊外洩
>* 完整性(Integrity)：資訊或系統之「正確性」，防制人為刻意竄改與自然雜訊干擾；防制假冒或未授權方式存取系統資源進行更改
>* 可用性(Availability)：資訊與資訊處理的「可獲得性」
>* 對於組織來說還要做到法規的遵循！
# 6.保護資訊C.I.A不同的技術與方法：
>* 機密性>存取控制、資料加解密
>* 完整性>存取控制、雜湊函數、數位簽章
>* 可用性>存取控制、容錯備援、備份、容量規劃、負載平衡
# 7.ISO 27000系列的資安標準：
>* -ISO/IEC 27018 《公有雲個人資料(PII)處理者之個資保護作業規範》
>* -ISO/IEC 27017 《雲端運算服務的資訊安全控制措施實務守則》
>* -CNS 2700x，目的在於制定一個可用來建立、實作、運作、監視、審查、維持及改進「資訊安全管理系統（ISMS）」
>* -雲端安全相關的ISO 27017、ISO 27018
# 8.資訊安全管理系統
>* -27001: ISO 27001:2013 ISMS驗證標準
>* -27002: ISO 27002:2013 工具書，明確建議應有哪些資訊安全控制措施
# ●請問下列哪個可以驗>ISO 27001

# Q&A
>* 學生入侵學校伺服器「竄改」期末考成績→完整性
>* 遭受駭客透過DDoS攻擊→可用性
>* 可用性的敘述>暫時無法使用網路
>* 非為成功建立資訊必要安全項目→導入ISO國際標準
>* 在資訊安全管理系統中內部查核不正確→稽核人員可稽核所屬單位，無須具備獨立性（SOD)
>* 展現最高管理階層對資訊安全管理系統之領導和承諾→確保資訊安全的要求已整合至組織的各項作業流程
>* 政策是不是每年都變→需要穩定（目標可能每年調）
>* PDCA不含何者→業務部門績效審核（資安不適業務審核,為衝突）
>* 請問下列何者不是公司資產→辦公桌
