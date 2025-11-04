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



### SSRF 

伺服器端請求偽造，可以請求到伺服器內網或是其他網域等



### Frontend Security
- XSS
- CSRF
- XSLeaks
- Lax + POST 
- JavaScript pseudo protocal  
- Context-aware XSS

### XSS
- 跨網站指令碼(cross-site scripting) 
- 讓別人的前端執行攻擊者的 JavaScript
- 常發生在未妥善處理輸入，進而被輸入XSS攻擊代碼 例： "html的input標籤 、 alert等


**XSS 分類(根據payload的來源)**
- Reflected XSS：從後端傳到前端，出現了XSS payload
- Stored XSS：payload 備取在database裡面，每次client請求就會出現XSS payload
- DOM-based XSS：使用DOM的操作在前端產生XSS payload 



**Reflected XSS**
![image.png](https://public-imgbed.pages.dev/file/1743675251379_image.png)
**Stored XSS**
![image.png](https://public-imgbed.pages.dev/file/1743675232285_image.png)

**DOM XSS**
![image.png](https://public-imgbed.pages.dev/file/1743675245721_image.png)



**常見的XSS Payload**
- fetch() 將資料傳出去
- document.cookie 拿到 Cookies
- html2canvas 可做到螢幕截圖
- keylogger
- alert
etc..


**XSS worm**
- 與一般XSS不同的是，他會選擇注入惡意 javascript 到其他客戶端，導致payload 在使用端互相注入
- 擴大危害的手法

**XSS prevent**
- HTML Sanitize
  - 將 HTML 中危險的部分處理掉
    - 但是很難將所有情況完美處理
- Dom purify
  - 被廣泛使用，已經很難在上面找到缺漏
    - 但不正確使用仍會造成資安問題
- CSP
  -透過網頁上規範白名單規則，讓瀏覽器控制對外部的請求


**CSP XSS prevent**
![image.png](https://public-imgbed.pages.dev/file/1743771551950_image.png)
![image.png](https://public-imgbed.pages.dev/file/1743778053004_image.png)
常見的CSP Directive
- default-src
- script-src
- image-src
- connect-src
- style-src
- navigate-to
![image.png](https://public-imgbed.pages.dev/file/1743771762893_image.png)


**CSP bypassing - via JSONP




**javascript 偽協議**

s








### Self-XSS
### Blind XSS 
XSS 在看不到的地方與不知道的時間點被執行





