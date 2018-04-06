# IoT Security TOP 10 物聯網十大安全測試
物聯網十大安全測試目標是幫助測試人員評估物聯網空間中的物聯網設備和應用程序。下面列出10項基本測試。但這不是全部的事項，但確保涵蓋這些基本原則將大大提高任何物聯網產品的安全性
## I1. Insecure Web Interface 不安全的網頁介面
- Assess any web interface to determine if weak passwords are allowed
- Assess the account lockout mechanism
- Assess the web interface for XSS, SQLi and CSRF vulnerabilities and other web application vulnerabilities
- Assess the use of HTTPS to protect transmitted information
- Assess the ability to change the username and password
- Determine if web application firewalls are used to protect web interfaces

## I2. Insufficient Authentication/Authorization 認證/授權不足
- Assess the solution for the use of strong passwords where authentication is needed
- Assess the solution for multi-user environments and ensure it includes functionality for role separation
- Assess the solution for Implementation two-factor authentication where possible
- Assess password recovery mechanisms
- Assess the solution for the option to require strong passwords
- Assess the solution for the option to force password expiration after a specific period
- Assess the solution for the option to change the default username and password

## I3. Insecure Network Services 不安全的網路服務
- Assess the solution to ensure network services don't respond poorly to buffer overflow, fuzzing or denial of service attacks
- Assess the solution to ensure test ports are are not present

## I4. Lack of Transport Encryption 缺少傳輸加密
- Assess the solution to determine the use of encrypted communication between devices and between devices and the internet
- Assess the solution to determine if accepted encryption practices are used and if proprietary protocols are avoided
- Assess the solution to determine if a firewall option available is available

## I5. Privacy Concerns 隱私問題
- Assess the solution to determine the amount of personal information collected
- Assess the solution to determine if collected personal data is properly protected using encryption at rest and in transit
- Assess the solution to determine if Ensuring data is de-identified or anonymized
- Assess the solution to ensure end-users are given a choice for data collected beyond what is needed for proper operation of the device

## I6. Insecure Cloud Interface 不安全的雲端介面
- Assess the cloud interfaces for security vulnerabilities (e.g. API interfaces and cloud-based web interfaces)
- Assess the cloud-based web interface to ensure it disallows weak passwords
- Assess the cloud-based web interface to ensure it includes an account lockout mechanism
- Assess the cloud-based web interface to determine if two-factor authentication is used
- Assess any cloud interfaces for XSS, SQLi and CSRF vulnerabilities and other vulnerabilities
- Assess all cloud interfaces to ensure transport encryption is used
- Assess the cloud interfaces to determine if the option to require strong passwords is available
- Assess the cloud interfaces to determine if the option to force password expiration after a specific period is available
- Assess the cloud interfaces to determine if the option to change the default username and password is available

## I7: Insecure Mobile Interface 不安全的行動介面
- Assess the mobile interface to ensure it disallows weak passwords
- Assess the mobile interface to ensure it includes an account lockout mechanism
- Assess the mobile interface to determine if it Implements two-factor authentication (e.g Apple's Touch ID)
- Assess the mobile interface to determine if it uses transport encryption
- Assess the mobile interface to determine if the option to require strong passwords is available
- Assess the mobile interface to determine if the option to force password expiration after a specific period is available
- Assess the mobile interface to determine if the option to change the default username and password is available
- Assess the mobile interface to determine the amount of personal information collected

## I8. Insufficient Security Configurability 安全配置性不足
- Assess the solution to determine if password security options (e.g. Enabling 20 character passwords or enabling two-factor authentication) are available
- Assess the solution to determine if encryption options (e.g. Enabling AES-256 where AES-128 is the default setting) are available
- Assess the solution to determine if logging for security events is available
- Assess the solution to determine if alerts and notifications to the user for security events are available

## I9. Insecure Software/Firmware 不安全的軟體與韌體
- Assess the device to ensure it includes update capability and can be updated quickly when vulnerabilities are discovered
- Assess the device to ensure it uses encrypted update files and that the files are transmitted using encryption
- Assess the device to ensure is uses signed files and then validates that file before installation

## I10. Poor Physical Security 實體安全考量不足
- Assess the device to ensure it utilizes a minimal number of physical external ports (e.g. USB ports) on the device
- Assess the device to determine if it can be accessed via unintended methods such as through an unnecessary USB port
- Assess the device to determine if it allows for disabling of unused physical ports such as USB
- Assess the device to determine if it includes the ability to limit administrative capabilities to a local interface only

> 參考資料: [\[IoT\]又愛又怕絨毛娃娃之簡單談IoT資安及OWASP IoT Top 10](https://laoomiaoo.blogspot.tw/2017/04/iotiotowasp-iot-top-10.html)
