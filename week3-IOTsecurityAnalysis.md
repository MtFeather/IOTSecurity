# 系統架構
![Analysis_tructure](images/Analysis_tructure.jpg)

# 本次實測軟體
> - elaticsearch: Elasticsearch 是一個即時的分佈式搜索分析引擎， 它能讓你以一個之前從未有過的速度和規模，去探索你的數據。它被用作全文檢索、結構化搜   索、分析以及這三個功能的組合。
> - kibana: 視覺與圖形化的表示方式來顯示各種log。
> - winlogbeat(windows)、logstash(linux): 幫助收集各地的log或是資訊，並且根據你的格式，轉換成各種資料欄位。

# 環境需求
## JAVA 8
### 1. 下載與安裝
- 下載網址: [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  ![JAVA](images/java.PNG)
### 2. 設定Java開發環境
Step1. 按下鍵盤『windows鍵+R』，開啟『執行』對話框，輸入『sysdm.cpl』，按下『確定』
![env_1](images/env_1.PNG)  
Step2. 在系統內容視窗中，點選如下圖所示的『進階』頁籤，及點擊『環境變數』  
![env_2](images/env_2.PNG)  
Step3. 在底下的系統變數中選擇Path，按下底下的『編輯』
![env_3](images/env_3.PNG)  
Step4. 點擊右邊的『新增』，輸入安裝的路徑，預設應該是"C:\Program Files\Java\jdk1.8.0_171\bin"，之後按下『確定』 
![env_4](images/env_4.PNG)   
### 3. 檢查設定成功
```cmd
javac -version
```
![java_version](images/java_version.PNG)

# 安裝伺服器系統
Elasticsearch + Kibana
## 安裝 Elasticsearch
下載網址: [https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.2.4.msi](https://artifacts.elastic.co/downloads/beats/winlogbeat/winlogbeat-6.2.4-windows-x86_64.zip)
### 開始安裝
Step1.  
![elastic_1](images/elastic_1.PNG)
Step2.  
![elastic_2](images/elastic_2.PNG)
Step3.  
![elastic_3](images/elastic_3.PNG)
### 啟動服務
- 使用系統管理員身分執行cmd移動到"C:\Program Files\Elastic\Elasticsearch\6.2.4\bin"
```cmd
cd C:\Program Files\Elastic\Elasticsearch\6.2.4\bin
```
- 執行啟動
```cmd
./elasticsearch.exe
```
### 檢查測試
- 在網站URL: [http://localhost:9200/](http://localhost:9200/)   
![elastic_test](images/elastic_test.PNG)

## 安裝 Kibana
### 下載安裝
- 下載網址: https://artifacts.elastic.co/downloads/kibana/kibana-6.2.4-windows-x86_64.zip
- 解壓縮後，我是將目錄與Elasticsearch放在同一層的目錄(C:\Program Files\Elastic)，並且將目錄去除後面的版本名稱
![kibana_1](images/kibana_1.PNG)
### 修改設定值
- 修改kibana目錄的config/kibana.yml，將`server.host`的註解拿掉，並把裡面的"localhost"換成"0.0.0.0"
```yml
server.host: "0.0.0.0"  # 0.0.0.0 表示綁定所有 IP
```
![kibana_2](images/kibana_2.PNG)
### 啟動服務
- 使用系統管理員身分執行cmd移動到"C:\Program Files\Elastic\kibana\bin"
```cmd
cd C:\Program Files\Elastic\kibana\bin
```
- 執行啟動
```cmd
./kibana.bat
```
### 檢查測試
- 在網站URL: [http://localhost:5601/](http://localhost:5601/)
![kibana_3](images/kibana_3.PNG)

# 安裝客戶端資料傳送軟體
Windows是winlogbeat，Linux是logstash
## 安裝 winlogbeat@Windows
### 下載及安裝
- 下載網址: [https://artifacts.elastic.co/downloads/beats/winlogbeat/winlogbeat-6.2.4-windows-x86_64.zip](https://artifacts.elastic.co/downloads/beats/winlogbeat/winlogbeat-6.2.4-windows-x86_64.zip)
- 解壓縮後，我是將目錄與Elasticsearch放在同一層的目錄(C:\Program Files\Elastic)，並且將目錄去除後面的版本名稱
![kibana_1](images/kibana_1.PNG)
- 執行原則  
Windows因為安全性的考量，在沒有更改過設定之前，是不允許執行 Windows PowerShell 的腳本檔。這就是所謂的「執行原則」。在預設狀態下，執行原則的設定值是 Restricted，也就是說你根本不能執行任何的 Windows PowerShell 腳本檔。  
「執行原則」有下列 4 種：  
  * Restricted ：關閉腳本檔的執行功能，這是預設的設定值。
  * AllSigned ：只允許執行受信任發行者簽署過的腳本檔。
  * RemoteSigned ：在本機電腦所撰寫的腳本檔，不需要簽署就可執行；但是從網際網路（例如：email、MSN Messenger）下載的腳本檔就必須經過受信任發行者的簽署才能執行。
  * Unrestricted ：任何腳本檔皆可被執行，但是於執行網際網路下載的腳本檔時，會先出現警告的提示視窗。





