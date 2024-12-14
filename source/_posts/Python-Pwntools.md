---
title: Python & Pwntools
date: 2024-11-19 13:59:45
tags: pwntools
---


# Python & Pwntools



## Base64 編碼

### Base64編解碼

需匯入 base64模組，語法：***import base64***

(2) Base64編碼方法：***b64encode(bytes字串)***，使用方法為<模組名稱>.<方法名稱>。
    如：***base64.b64encode(b'ABCD')*** ⇒ b'QUJDRA==’    
    註：b前綴的用意為將字元字串轉為python3專用bytes字串
(3) Base64解碼方法：***b64decode(base64編碼字串)，***如：***base64.b64decode(b'TWFu')*** ⇒ b'Man’

### 字元字串與bytes字串的差別
(1) 字元字串用於處理文字資料，bytes字串用於處理網路資料、電腦檔案等二進位資料。

(2) 字元字串的元素是Unicode字元，bytes字串的元素是0~255的整數(8位元)。

(3) 在Python中，可用前綴 u 或 U 來表示一個字元字串，如：u’Hello’。

(4) 在Python中，可用前綴 b 或 B 來表示一個bytes字串，如：b’Hello’。




## Python 結合資安應用

> ### pwntools 相關語法與功能
- **interactive**
- **recvline**
- **sendline**
- **encode & decode**
- **remote**







