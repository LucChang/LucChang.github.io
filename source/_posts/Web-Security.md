---
title: Web Security
date: 2025-01-08 09:15:34
tags: web
---
# Web Security
### HTTP
**HTTP status code**
- 2xx 一切正常
- 3xx 重新導向
- 4xx 客戶端錯誤
- 5xx 伺服器錯誤


### Web Attack
- Frontend 瀏覽器
  - XSS
  - CSS injection
  - prototype pollution
  - Dom Clobbering
- Backend
  - LFI
  - Command injection
  - SQL injection
  - Serializtion
  - SSRF
  - SSTI
- https://github.com/w181496/Web-CTF-Cheatsheet (攻擊手法)

### Cookie
**用途**
紀錄使用者資訊在瀏覽器內，紀錄不同網站造訪的cookie，用途是可以記錄使用者資訊，下次造訪會記錄你之前造訪的狀態，透過Name和value的參數紀錄
**Session**
在後端會有一個亂碼叫做session id，對應到使用者的Data，這些使用者Data會被儲存到server database，前端的cookie會設置session id，發送http 請求時後端會去對照cookie的session id，從Database取得使用者資訊，這種機制讓駭客無法去冒充他人身分

### Recon  
**檢查四網站伺服器類型**
- 從 Error message 觀察後端與版本
  - https://0xdf.gitlab.io/cheatsheets/404
- webanalyzer 
  - https://chromewebstore.google.com/detail/wappalyzer-technology-pro/gppongmhjkpfnbhagpmjfkannfbllamg

### INFO leak


**robots.txt**
告訴爬蟲哪些路徑能爬，哪些不行
有可能會洩漏敏感路徑！
- ex. 管理後臺、備份檔路徑

**Git Leak**
版本控制系統
可還原網站原始碼
- 工具 https://github.com/lijiejie/GitHack

**google hacking**

![image.png](https://public-imgbed.pages.dev/file/1736316233341_image.png)

註：https://www.exploit-db.com/google-hacking-database


### Web Sell
**Web 兩種型態**

File-base：將檔案映射到檔案路徑下

route base：定義路由，會有對應的function，並且到路由的路徑時就會運行function


![image.png](https://public-imgbed.pages.dev/file/1739931892435_image.png)

### Path Traversal 

在一個路徑下有一個?file=xx.xx的檔案，這時候可以透過直覺透過../../../去道不同的路徑





### LFI (Local File Inclution)

- 一個php的檔案被include，但是因為重要資運被註解了，所以被parse之後就消失了，透過php filter chain 創造不同的編碼方式，像是將php編碼成base64 code讓檔案不會被parse
使用方式：php://filter/read=string.rot13|covert.base64-encode/resource=
string.rot13|covert.base64-encode(編碼方式透過|pipeline讓字串用不同的方式編碼，所以可以透過編碼的方式構造出一個RCE的code)
參考資料：
- https://github.com/synacktiv/php_filter_chain_generator/blob/main/php_filter_chain_generator.py
- https://github.com/wupco/PHP_INCLUDE_TO_SHELL_CHAR_DICT

### Injection 

- Code Injection
- Command Injection 
- Argument Injection
- SQL Injection
- NoSQL Injection
- Server side template Injection(SSTI)
- CRLF Injection
- Css Injection


**code Injection**




### Augment Injection

### Web Reverse

Webhook reference


###  SQL injection 
![image.png](https://public-imgbed.pages.dev/file/1741274816492_image.png)
![image.png](https://public-imgbed.pages.dev/file/1741274903738_image.png)
![image.png](https://public-imgbed.pages.dev/file/1741274940100_image.png)

**SQL injection**

- Stacked：用分號隔開各種句子
- Union：前面的輸出和後面的輸出連在一起
- Time：透過Sleep來判斷條件
- Boolean：透過布林直結果來判斷條件
- Error Based：透過錯誤訊息來取得資料
- Out of Band：讀檔、寫檔
reference：https://github.com/w181496/Web-CTF-Cheatsheet?tab=readme-ov-file#php-%E5%85%B6%E4%BB%96%E7%89%B9%E6%80%A7
**SQL 與 NoSQL(Not Only SQL)**
比較：NoSQL不需要提定義schema節
![image.png](https://public-imgbed.pages.dev/file/1741311849826_image.png)

Blind Base：Blind-Base 的核心在於利用與法規則來獲得部分答案的正確性，從而迭帶出答案

