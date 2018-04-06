# IoT Vulnerabilities Project 物聯網漏洞項目
|  漏洞  | 攻擊面向 | 概要 |
| :----: | ------- | ---- |
| Username Enumeration<br/>(用戶名列舉) | <li>Administrative Interface</li><li>Device Web Interface</li><li> Cloud Interface</li><li>Mobile Application</li> | <li>能夠通過認證交互收集一組有效的用戶名</li> |
| Weak Passwords<br/>(弱密碼) | <li>Administrative Interface</li><li>Device Web Interface</li><li>Cloud Interface</li><li>Mobile Application</li> | <li>像是允許將帳戶密碼設置為“1234”或“123456”</li><li>使用預先編程的默認密碼</li> |
| Account Lockout<br/>(帳號鎖定) | <li>Administrative Interface</li><li>Device Web Interface</li><li>Cloud Interface</li><li>Mobile Application</li> | <li>能夠在 3 至 5 次登錄嘗試失敗後，繼續發送身份驗證嘗試</li> |
| Unencrypted Services<br/>(非加密服務) | <li>Device Network Services</li> | <li>網絡服務未作適當加密來防止攻擊者竊聽或篡改</li> |
| Two-factor Authentication<br/>(雙因素認證) | <li>Administrative Interface</li><li>Cloud Web Interface</li><li>Mobile Application</li> | <li>缺少雙因素認證機制，如安全認證或指紋掃描器</li> |
| Poorly Implemented Encryption<br/>(輕度加密) | <li>Device Network Services</li> | <li>雖然已執行加密，但是該配置不正確或未被能準確更新。例如使用 SSL v2</li> |
| Update Sent Without Encryption<br/>(非加密更新) | <li>Update Mechanism</li> | <li>更新是在沒有使用 TLS 或加密情況下通過網絡傳輸更新文件的</li> |
| Update Location Writable<br/>(更新位置為可寫) | <li>Update Mechanism</li> | <li>更新文件的存儲位置是世界可寫的，可能允許修改固件並將其分發給所有用戶</li> |
| Denial of Service<br/>(拒絕服務) | <li>Device Network Services</li> | <li>可以以拒絕服務或整個設備的方式來攻擊服務</li> |
| Removal of Storage Media<br/>(刪除儲存介質) | <li>Device Physical Interfaces</li> | <li>能夠從設備中物理移除存儲介質</li> |
| No Manual Update Mechanism<br/>(沒有手動更新機制) | <li>Update Mechanism</li></li> | <li>無法手動強制更新檢查設備</li> |
| Missing Update Mechanism<br/>(缺少更新機制) | <li>Update Mechanism</li> | 無法更新設備 |
| Firmware Version Display and/or Last Update Date<br/>(韌體版本顯示或是最後更新日期) | <li>Device Firmware</li> | <li>當前韌體版本不顯示和/或上次更新日期不顯示</li> |
| Firmware and storage extraction<br/>(韌體和存儲提取) | <li>JTAG / SWD interface</li><li>[In-Situ dumping](https://www.flashrom.org/Flashrom)</li><li>Intercepting a OTA update</li><li>Downloading from the manufacturers web page</li><li>[eMMC tapping](https://www.exploitee.rs/index.php/Exploitee.rs_Low_Voltage_e-MMC_Adapter)</li><li>Unsoldering the SPI Flash / eMMC chip and reading it in a adapter</li>





