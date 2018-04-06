# IoT Vulnerabilities Project 物聯網漏洞項目
|  漏洞  | 攻擊面向 | 概要 |
| :----: | --------------------- | ---- |
| Username Enumeration<br/>(用戶名列舉) | <li>Administrative Interface</li><li>Device Web Interface</li><li> Cloud Interface</li><li>Mobile Application</li> | <li>能夠通過認證交互收集一組有效的用戶名</li> |
| Weak Passwords<br/>(弱密碼) | <li>Administrative Interface</li><li>Device Web Interface</li><li>Cloud Interface</li><li>Mobile Application</li> | <li>像是允許將帳戶密碼設置為“1234”或“123456”</li><li>使用預先編程的默認密碼</li> |
| Account Lockout<br/>(帳號鎖定) | - Administrative Interface<br/>- Device Web Interface<br/>- Cloud Interface<br/>- Mobile Application | -  能夠在 3 至 5 次登錄嘗試失敗後，繼續發送身份驗證嘗試 |
| Unencrypted Services<br/>(非加密服務) | - Device Network Services | - 網絡服務未作適當加密來防止攻擊者竊聽或篡改 |
| Two-factor Authentication<br/>(雙因素認證) | - Administrative Interface<br/>- Cloud Web Interface<br/>- Mobile Application | - 缺少雙因素認證機制，如安全認證或指紋掃描器 |
| Poorly Implemented Encryption<br/>(輕度加密) | - Device Network Services | - 雖然已執行加密，但是該配置不正確或未被能準確更新。例如使用 SSL v2  |
| Update Sent Without Encryption<br/>(非加密更新) | - Update Mechanism | -更新是在沒有使用 TLS 或加密情況下通過網絡傳輸更新文件的 |
| Update Location Writable<br/>(更新位置為可寫) | - Update Mechanism | - 更新文件的存儲位置是世界可寫的，可能允許修改固件並將其分發給所有用戶 |

