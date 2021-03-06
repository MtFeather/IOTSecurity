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
- 修改執行原則  
Windows因為安全性的考量，在沒有更改過設定之前，是不允許執行 Windows PowerShell 的腳本檔。這就是所謂的「執行原則」。在預設狀態下，執行原則的設定值是 Restricted，也就是說你根本不能執行任何的 Windows PowerShell 腳本檔。  
「執行原則」有下列 4 種：  
  * Restricted ：關閉腳本檔的執行功能，這是預設的設定值。
  * AllSigned ：只允許執行受信任發行者簽署過的腳本檔。
  * RemoteSigned ：在本機電腦所撰寫的腳本檔，不需要簽署就可執行；但是從網際網路（例如：email、MSN Messenger）下載的腳本檔就必須經過受信任發行者的簽署才能執行。
  * Unrestricted ：任何腳本檔皆可被執行，但是於執行網際網路下載的腳本檔時，會先出現警告的提示視窗。
```powershell
Set-ExecutionPolicy RemoteSigned
```
![winlogbeat_1](images/winlogbeat_1.PNG)
- 安裝
```powershell
cd 'C:\Program Files\Elastic\winlogbeat'
.\install-service-winlogbeat.ps1
```
![winlogbeat_2](images/winlogbeat_2.PNG)
### 修改設定檔
- 修改"C:\Program Files\Elastic\winlogbeat.yml"檔案
```yml
###################### Winlogbeat Configuration Example ##########################

# This file is an example configuration file highlighting only the most common
# options. The winlogbeat.reference.yml file from the same directory contains all the
# supported options with more comments. You can use it as a reference.
#
# You can find the full configuration reference here:
# https://www.elastic.co/guide/en/beats/winlogbeat/index.html

#======================= Winlogbeat specific options ==========================

# event_logs specifies a list of event logs to monitor as well as any
# accompanying options. The YAML data type of event_logs is a list of
# dictionaries.
#
# The supported keys are name (required), tags, fields, fields_under_root,
# forwarded, ignore_older, level, event_id, provider, and include_xml. Please
# visit the documentation for the complete details of each option.
# https://go.es.io/WinlogbeatConfig
winlogbeat.event_logs:
  - name: Application
    ignore_older: 72h
  - name: Security
  - name: System

#==================== Elasticsearch template setting ==========================

setup.template.settings:
  index.number_of_shards: 3
  #index.codec: best_compression
  #_source.enabled: false

#================================ General =====================================

# The name of the shipper that publishes the network data. It can be used to group
# all the transactions sent by a single shipper in the web interface.
#name:

# The tags of the shipper are included in their own field with each
# transaction published.
#tags: ["service-X", "web-tier"]

# Optional fields that you can specify to add additional information to the
# output.
#fields:
#  env: staging


#============================== Dashboards =====================================
# These settings control loading the sample dashboards to the Kibana index. Loading
# the dashboards is disabled by default and can be enabled either by setting the
# options here, or by using the `-setup` CLI flag or the `setup` command.
#setup.dashboards.enabled: false

# The URL from where to download the dashboards archive. By default this URL
# has a value which is computed based on the Beat name and version. For released
# versions, this URL points to the dashboard archive on the artifacts.elastic.co
# website.
#setup.dashboards.url:

#============================== Kibana =====================================

# Starting with Beats version 6.0.0, the dashboards are loaded via the Kibana API.
# This requires a Kibana endpoint configuration.
setup.kibana:

  # Kibana Host
  # Scheme and port can be left out and will be set to the default (http and 5601)
  # In case you specify and additional path, the scheme is required: http://localhost:5601/path
  # IPv6 addresses should always be defined as: https://[2001:db8::1]:5601
  host: "localhost:5601"

#============================= Elastic Cloud ==================================

# These settings simplify using winlogbeat with the Elastic Cloud (https://cloud.elastic.co/).

# The cloud.id setting overwrites the `output.elasticsearch.hosts` and
# `setup.kibana.host` options.
# You can find the `cloud.id` in the Elastic Cloud web UI.
#cloud.id:

# The cloud.auth setting overwrites the `output.elasticsearch.username` and
# `output.elasticsearch.password` settings. The format is `<user>:<pass>`.
#cloud.auth:

#================================ Outputs =====================================

# Configure what output to use when sending the data collected by the beat.

#-------------------------- Elasticsearch output ------------------------------
output.elasticsearch:
  # Array of hosts to connect to.
  hosts: ["localhost:9200"]

  # Optional protocol and basic auth credentials.
  #protocol: "https"
  #username: "elastic"
  #password: "changeme"

#----------------------------- Logstash output --------------------------------
#output.logstash:
  # The Logstash hosts
  #hosts: ["localhost:5044"]

  # Optional SSL. By default is off.
  # List of root certificates for HTTPS server verifications
  #ssl.certificate_authorities: ["/etc/pki/root/ca.pem"]

  # Certificate for SSL client authentication
  #ssl.certificate: "/etc/pki/client/cert.pem"

  # Client Certificate Key
  #ssl.key: "/etc/pki/client/cert.key"

#================================ Logging =====================================

# Sets log level. The default log level is info.
# Available log levels are: error, warning, info, debug
#logging.level: debug

# At debug level, you can selectively enable logging only for some components.
# To enable all selectors use ["*"]. Examples of other selectors are "beat",
# "publish", "service".
#logging.selectors: ["*"]

#============================== Xpack Monitoring ===============================
# winlogbeat can export internal metrics to a central Elasticsearch monitoring
# cluster.  This requires xpack monitoring to be enabled in Elasticsearch.  The
# reporting is disabled by default.

# Set to true to enable the monitoring reporter.
#xpack.monitoring.enabled: false

# Uncomment to send the metrics to Elasticsearch. Most settings from the
# Elasticsearch output are accepted here as well. Any setting that is not set is
# automatically inherited from the Elasticsearch output configuration, so if you
# have the Elasticsearch output configured, you can simply uncomment the
# following line.
#xpack.monitoring.elasticsearch:

logging.to_files: true
logging.files:
  path: C:/ProgramData/winlogbeat/Logs
logging.level: info
```
### 測試
```powershell
cd 'C:\Program Files\Elastic\winlogbeat'
.\winlogbeat.exe test config -c .\winlogbeat.yml -e
```
![winlogbeat_3](images/winlogbeat_3.PNG)

```powershell
.\winlogbeat setup --template -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'
```
![winlogbeat_4](images/winlogbeat_4.PNG)
- 查看URL:[http://localhost:9200/winlogbeat-\*](http://localhost:9200/winlogbeat-*)
![winlogbeat_5](images/winlogbeat_5.PNG)

```powershell
.\winlogbeat setup --dashboards
```
![winlogbeat_6](images/winlogbeat_6.PNG)
- 啟動winlogbeat服務
```powershell
Start-Service winlogbeat
```
![winlogbeat_7](images/winlogbeat_7.PNG)
- 在kibana看到的結果
![winlogbeat_8](images/winlogbeat_8.PNG)

## 安裝 logstash@Ubuntu MATE (64-bit)
- 安裝JAVA 8
```bash
sudo apt-get install openjdk-8-jre openjdk-8-jdk
```
- 下載安裝logstash
```bash
sudo apt-get install grok
curl -L -O https://artifacts.elastic.co/downloads/logstash/logstash-5.2.0.zip
unzip logstash-5.2.0.zip
sudo mv logstash-5.2.0/ /opt
cd /opt 
sudo mv logstash-5.2.0/ logstash
```
```bash
sudo apt-get install ant texinfo openjdk-8-jdk build-essential
git clone https://github.com/jnr/jffi.git
cd jffi
ant jar
sudo cp build/jni/libjffi-1.2.so /opt/logstash/vendor/jruby/lib/jni/arm-Linux
```
- 修改設定檔
```bash
cd /opt/logstash
sudo vim config/jvm.options
-----------------------------
-Xms256m
-Xmx512m
-----------------------------

sudo vim apache-filter.conf 
-----------------------------
input {
  file {
    path => "/var/log/apache2/access.log"
    start_position => "beginning"
  }
}

filter {
  if [path] =~ "access" {
    mutate { replace => { "type" => "apache_access" } }
    grok {
      match => { "message" => "%{COMBINEDAPACHELOG}" }
    }
  }
  date {
    match => [ "timestamp" , "dd/MMM/yyyy:HH:mm:ss Z" ]
  }
}

output {
  elasticsearch {
    hosts => ["192.168.1.56:9200"]
  }
  stdout { codec => rubydebug }
}
-----------------------------
```
