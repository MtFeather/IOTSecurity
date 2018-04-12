# 期末專案:物聯網設備的攻擊實測
## Web Attacks漏洞測試
### 1.  測試DVWA/command injection
![command_injection_1.PNG](images/command_injection_1.PNG)
cat /var/log/apache2/access.log #Bash
```
192.168.10.59 - - [12/Feb/2016:03:22:59 +0800] "GET /DVWA/dvwa/css/main.css HTTP/1.1" 200 1447 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:22:59 +0800] "GET /DVWA/dvwa/images/logo.png HTTP/1.1" 200 5332 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:23:20 +0800] "POST /DVWA/vulnerabilities/exec/ HTTP/1.1" 200 1959 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:23:24 +0800] "GET /DVWA/dvwa/css/main.css HTTP/1.1" 200 1447 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:23:24 +0800] "GET /DVWA/dvwa/js/dvwaPage.js HTTP/1.1" 200 811 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:23:24 +0800] "GET /DVWA/dvwa/images/logo.png HTTP/1.1" 200 5332 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:18 +0800] "POST /DVWA/vulnerabilities/exec/ HTTP/1.1" 200 1965 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:21 +0800] "GET /DVWA/dvwa/css/main.css HTTP/1.1" 200 1447 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:21 +0800] "GET /DVWA/dvwa/js/dvwaPage.js HTTP/1.1" 200 811 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:21 +0800] "GET /DVWA/dvwa/images/logo.png HTTP/1.1" 200 5332 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:47 +0800] "POST /DVWA/vulnerabilities/exec/ HTTP/1.1" 200 2845 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:50 +0800] "GET /DVWA/dvwa/js/dvwaPage.js HTTP/1.1" 200 811 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:50 +0800] "GET /DVWA/dvwa/css/main.css HTTP/1.1" 200 1447 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:40:50 +0800] "GET /DVWA/dvwa/images/logo.png HTTP/1.1" 200 5332 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:42:18 +0800] "POST /DVWA/vulnerabilities/exec/ HTTP/1.1" 200 1964 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:42:21 +0800] "GET /DVWA/dvwa/css/main.css HTTP/1.1" 200 1447 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:42:21 +0800] "GET /DVWA/dvwa/js/dvwaPage.js HTTP/1.1" 200 811 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
192.168.10.59 - - [12/Feb/2016:03:42:21 +0800] "GET /DVWA/dvwa/images/logo.png HTTP/1.1" 200 5332 "http://120.114.140.30/DVWA/vulnerabilities/exec/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"
```
