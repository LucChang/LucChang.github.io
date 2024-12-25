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



**OTP**
- RNG (Random Number Generator)
- 一次性密碼本，必須是 Truly Random 產生
- 理論上被證明具有完善保密性
- 密碼至少要和資料一樣長
- 只能被用一次，用完就要丟
- 傳輸密碼本的通道必須安全


**LCG** (待筆記)




**Mersenne Twister 梅森旋轉算法**
生成亂數方法
- 輸入 seed 擴展成 624 個 state
- 以舊的 state 生成下一輪 state
- 取 state 值加料後輸出隨機值
- state 用完了從第二步驟重複

**/dev/radnom**
- 類UNIX系統中是一個特殊的裝置檔案，可以用作亂數發生















