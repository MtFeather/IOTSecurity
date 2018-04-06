# IoT Attack Surface Areas 物聯網攻擊面向
> 物聯網的發展面向會更廣，尤其是當裝置感測器更多元，系統彼此間更開放互連，並能與各式應用服務相結合，攻擊面向也將更廣，譬如感測收集到的資料被入侵修改，也 將牽動後端的資訊反饋出問題，進而導致其他間接攻擊等行為發生。
>
> 參考資料: [連網設備激增，威脅將無所不在](https://www.ithome.com.tw/news/114126)
## Ecosystem Access Control 生態系統訪問控制
- Implicit trust between components
- Enrollment security
- Decommissioning system
- Lost access procedures
## Device Memory 設備的記憶體
- Cleartext usernames
- Cleartext passwords
- Third-party credentials
- Encryption keys
## Device Physical Interfaces 設備的實體存取介面
- Firmware extraction
- User CLI
- Admin CLI
- Privilege escalation
- Reset to insecure state
- Removal of storage media
## Device Web Interface 設備的網頁介面
- SQL injection
- Cross-site scripting
- Cross-site Request Forgery
- Username enumeration
- Weak passwords
- Account lockout
- Known default credentials
## Device Firmware 設備的韌體
- Hardcoded credentials
- Sensitive information disclosure
- Sensitive URL disclosure
- Encryption keys
- Firmware version display and/or last update date
## Device Network Services 設備的網路服務
- Information disclosure
- User CLI
- Administrative CLI
- Injection
- Denial of Service
- Unencrypted Services
- Poorly implemented encryption
- Test/Development Services
- Buffer Overflow
- UPnP
- Vulnerable UDP Services
- DoS
## Administrative Interface 管理介面
- SQL injection
- Cross-site scripting
- Cross-site Request Forgery
- Username enumeration
- Weak passwords
- Account lockout
- Known default credentials
- Security/encryption options
- Logging options
- Two-factor authentication
- Inability to wipe device
