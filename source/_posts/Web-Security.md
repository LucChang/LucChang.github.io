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