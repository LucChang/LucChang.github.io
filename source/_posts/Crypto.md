---
title: Crypto
date: 2024-12-11 01:26:44
tags: 密碼學
---

# Crypto


## Encrpytion

### Symmetric-key algorithm

- 對稱密碼加密
- 加解密使用同意把金鑰
- 加解密的速度快

### Stream cipher
- 又稱資料流加密、流加密
- 通常是以bit為單位做Xor 運算



**Synchronous stream cipher**
- RC4 (Rivest Cipher)
- 

**Self-Synchronous stream cipher**



**OTP(one time password)**
- RNG (Random Number Generator)
- 一次性密碼本，必須是 Truly Random 產生
- 理論上被證明具有完善保密性
- 密碼至少要和資料一樣長
- 只能被用一次，用完就要丟
- 傳輸密碼本的通道必須安全


**LCG** (待筆記)
公式：Xn+1 = (aXn + b) mod m
加密方法
- 線性同餘方法
- 運算速度快、易寫、佔用記憶體少

解密：
通常在式a, b, m等未知數都不知道時

思路：需要先求出 m
如果能拿到足夠多 m 的倍數 m1, m2, m3…
gcd(m1, m2, m3, …) 大概率會算出 m
先找到 m 的倍數 (需要消掉 a)
t0 = x0 - x1 (mod m)
t1 = x1 - x2 = a * (x0 - x1) = a * t0 (mod m)
t2 = x2 - x3 = a * (x1 - x2) = a * t1 (mod m)
→ t0 * t2 - t1 * t1 = t0 * (a2 * t0) - (a * t0) * (a * t0) = 0 (mod m)
生出一堆 m 的倍數
m1 = (x0 - x1) * (x2 - x3) - (x1 - x2) * (x1 - x2)
m2 = (x1 - x2) * (x3 - x4) - (x2 - x3) * (x2 - x3)
m3 = (x2 - x3) * (x4 - x5) - (x3 - x4) * (x3 - x4)



**Mersenne Twister 梅森旋轉算法**
生成亂數方法
- 輸入 seed 擴展成 624 個 state
- 以舊的 state 生成下一輪 state
- 取 state 值加料後輸出隨機值
- state 用完了從第二步驟重複

**/dev/radnom**
- 類UNIX系統中是一個特殊的裝置檔案，可以用作亂數發生




### AES
**Block mode**

**ECB mode:**
將要加密的東西分成不同的block，每個block有可能是16bits, 32bits或是64bits，每個block都加密後隨便組合 

**OFB mode:**

**CFB mode:**












