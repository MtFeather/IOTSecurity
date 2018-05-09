# 系統架構
![Analysis_tructure](images/Analysis_tructure.jpg)

# 本次實測軟體
> - elaticsearch: Elasticsearch 是一個即時的分佈式搜索分析引擎， 它能讓你以一個之前從未有過的速度和規模，去探索你的數據。它被用作全文檢索、結構化搜   索、分析以及這三個功能的組合。
> - kibana: 視覺與圖形化的表示方式來顯示各種log。
> - winlogbeat(windows)、logstash(linux): 幫助收集各地的log或是資訊，並且根據你的格式，轉換成各種資料欄位。

# 環境需求
## JAVA 8
### 1. 下載與安裝
  下載網址: [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
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
