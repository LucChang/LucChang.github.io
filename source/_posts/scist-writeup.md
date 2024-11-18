---
title: Basic Linux
date: 2024-11-06 19:23:27
tags: Linux
---

# Linux

> ## Basic Linux Command
- **pwd**: Display the current working directory. (print work directory)  
- **ls**: List directory contents. (list)  
- **cd**: Change the current directory. (change directory)  
- **mkdir**: Create a new directory. (make directory)  
- **touch**: Create a new, empty file.  
- **rm**: Delete files or directories. (remove)  
- **cp**: Copy files or directories. (copy)  
- **mv**: Move or rename files or directories. (move)  
- **cat**: Display the contents of a file. (concatenate)



> ## The Git Command

- **git clone + (Github URL)**
- **git add + (File)**
- **git add + .**
- **git commit -m + (Add initial project files)**  
- **git status**
- **git push origin main**
- **git pull origin main**
- **git branch feature-branch**
- **git checkout feature-branch**
- **git merge feature-branch**

> ## apt (Advanced Packing Tool)
I kind of downloading tool, often use in Debian operating system
- **sudo apt update** (update the things you can download)
- **sudo apt upgrade** (upgrade the things that have downloaded)


> ## Network and Remote Acess
- **ping**: Send ICMP ECHO_REQUEST to network hosts (To check whether the Ip address(or host) exist, and check connection status) ex. 
- **wget**: 下載檔案能夠在Terminal裡面編輯 wget https://www.example.com -O hello.txt
- **curl**： 與伺服器端進行互動，像是可以向伺服器進行POST或是GET等操作
- **ssh**: 連線到一台機器進行遠端操控等  ex. ssh -p 2222 user@youripaddress  port是依照不同機器有自己的port也可以自己設定
- **scp**: 與ssh相似，可以將其他機器的檔案傳輸、複製到自己目前所用的機器 ex. scp user@youripaddress:file_path ./



> ## System Information and Monitoring 
- **whoami**

> ## Piping and Redirection
- **|**: 將目前的結果傳至下一個指令 ex. cat flag | rev
- **>**: 將要寫的東西寫入某個檔案 ex. echo "hello" > hello.txt  
- **>>**: 在已存在的檔案進行近一步的編寫，不會將之前的內容覆蓋 ex. echo "hello >> hello.txt
### 額外常與 piping 和 Redirecting 的參數
- **less** 
- **more**
- **head**
- **tail**
使用方式：find --help | less or more or head or tail

> ## vim 
- **i**: (insert) 按下這個鍵位時即可編輯程式碼
- **esc**: 退出編輯模式，可以執行其他的指令或是其他操作等
- **:**: 當按下esc後可以按下這個鍵，即可打入你想要搭配的指令像是q、w等
- **y**:
- **p**:
- **d**:
- **v**:

> ## Shell Script
### **Bash**: Shell Script內部函式，可以執行Shell Script檔案


> ## rar & zip & tar 壓縮檔差別
### rar

### zip

### tar

> ## Command
find . -perm /4000 2>/dev/null
將錯誤訊息redirect到其他的路徑"2"代表錯誤訊息



> ## Hash
hashcat -m 0 yourfile.txt /usr/share/wordlists/rockyou.txt hash爆破法

> ## hydra

防禦方式: 透過pulickey生成一個密碼與遠端裝置的密碼是同一個pair，所以就不是單純用密碼就能夠登入到遠端的機器，同時也會認裝置




