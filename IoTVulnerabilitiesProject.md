# IoT Vulnerabilities Project 物聯網漏洞項目
|  漏洞  | 攻擊面向 | 概要 |
| :----: | ------- | ---- |
| Username Enumeration<br/>(用戶名列舉) | - Administrative Interface<br/>- Device Web Interface<br/>- Cloud Interface<br/>- Mobile Application | - 能夠通過認證交互收集一組有效的用戶名。
| Weak Passwords<br/>(弱密碼) | - Administrative Interface<br/>- Device Web Interface<br/>- Cloud Interface<br/>- Mobile Application | - 像是允許將帳戶密碼設置為“1234”或“123456”。<br/>- 使用預先編程的默認密碼。 |
| Account Lockout<br/>(帳號鎖定) | - Administrative Interface<br/>- Device Web Interface<br/>- Cloud Interface<br/>- Mobile Application | -  能夠在 3 至 5 次登錄嘗試失敗後，繼續發送身份驗證嘗試。 |
| Unencrypted Services<br/>(非加密服務) | - Device Network Services | - 網絡服務未作適當加密來防止攻擊者竊聽或篡改。 |
| Two-factor Authentication<br/>(雙因素認證) | - Administrative Interface<br/>- Cloud Web Interface<br/>- Mobile Application | 缺少雙因素認證機制，如安全認證或指紋掃描器。 |
