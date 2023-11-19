# RPAEMILY

## Emily_Low-Code 
- 低度程式碼，這邊採用javaScript作為Low-Code程式語言，與小學Scratch一樣等級
- 先打開Emily-->訓練圖像-->工作資料夾執行腳本-->寫完程式看debug-->開啟console-->開TEST看剛剛的程式碼執行狀況
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/7c0f6631-5863-4676-976d-60085ec2d720)
- 將資料放到"C:\Users\tomsu\AppData\Roaming\webbot\tmp\file.txt"(工作資料夾)，在使用input就可已將資料載入；input.file(檔名)則就可以把裡面的文字讀出來
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/85692f49-70b7-4c0c-b6e1-410cf53098a3)
- 
## JS 基礎
- Statement / Comment :console.log("Hello World"); 這是一個完整的程式碼Statement，用.取用，中括弧為放入的東西，；則是代表結束，//代表註解
- 常數 : const text = "Hello World"；這樣就是宣告text常數--> console.log(text)，常數被指定後無法再被改變
- 變數 : let text = "Hello World"；可以再往下更改text內容
- 基本資料型別:STRING / NUMBER(let n = 100;) / BOOLEAN(let condition = true;) / UNDEFINED (let temp;)
- 運算子 (+ - * / > < >= <= === !== ) (condition && true)-->剛condition為true，所以"並且"的涵義就會是Trule，如果是 (condition && false)就會是false / (condition || false) 這是或者就會True / (text + ",this is Jerry")將前後字串用+串起來
- 複雜資料型別:OBJECT : let obj = {key1:"text",key2:100} console.log(obj)
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/711ba455-5447-443e-9961-5b4972c1b151)
- ARRAY : let arry = ["text",100] console.log(arry[1])
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/bfabef18-6022-4333-9b9f-8f7ce5dacd31)
- 函式: FUNCTION: 自訂function方式 function add(a,b) {return a + b;} console.log(add(1,2));

## 工具函式庫
- api : 到amily執行工作
- 如果要產檔案，也可以output.file2 = "test";
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/17618eaf-2317-40ec-9453-fd55a646be39)
- 用api的做法 : let filetxt = api.read("file.txt");
- api.write("file3.txt","write test")
- MATH函式庫 : let result = Math.round(1.23); console.log(result);
- JSON函式庫 : let obj = {key1:"text",key2:100}  ； let strObj = JSON.stringify(obj) 這是一個標準的JSON寫成文字的語法 --> 再用api.write("obj.txt",strObj) 產出文字檔
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/9e9b0b8c-1ba2-4e58-8455-d13b795ba0de)
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/012905a0-0205-4d78-8c43-7ee5ac6e363c)
- lodash函式庫 補足javascript中的一些不足
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/3edf8b4b-645a-469d-b2da-0975c52ff014)


## Web Automation
### 開發簡單自動化瀏覽器功能
- 1.範例將網頁查詢存取成PDF:通常會先將工作資料夾清除>先將要讓RPA待會要帶入的資訊文字檔案用匯入夾帶上 > 插入文字(keyword) > 帶入keyword>到達後存取成PDF(列印圖示)
- 2.範例保存內容與環境變數的使用:通常會先將工作資料夾清除>先將要讓RPA待會要帶入的資訊文字檔案用匯入夾帶上 > 插入文字(keyword) > 帶入keyword > 選擇保存內容(文字/圖案/檔案/截圖) >點選你要截下的位置(返成粉紅色)>檔名設置為%keyword%-範例 
- 3.範例循環表格工作:先將工作資料夾清除>先將要讓RPA待會要帶入的資訊CSV檔案用匯入夾帶上> 選擇循環工作(一般CSV是逗號分隔)(表頭位在第一列設置為0) > tmp會自動生成row-表頭(這樣這文字檔就可以被其他模組流程使用)> 插入文字(keyword) > > 選擇保存內容(文字/圖案/檔案/截圖) >點選你要截下的位置(返成粉紅色)>檔名設置為%row-股票%-股價 就會依照你的keyword設置為檔名> !這邊要注意，循環抓取網頁的各列資訊，位置要在網頁上是固定的，否則將會存取到當下位置的文字資訊。
- 4.範例等待數秒(像是網頁載入比較慢，讓RPA等待再繼續)，例如轉換PDF檔案成JPG時，將檔案上傳後，要等待數秒才能轉換(https://smallpdf.com/pdf-to-jpg，在這個地方就可以點下IDLE(鬧鐘圖案)，等到download的圖示出現
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/1e7668ae-0a56-486b-905f-6f73e23142e1)
- 5.範例等待節點，跟4類似只是點下wait(準芯圖示)，點選後續要按下去的逾時秒數，例如點下Download，最慢等待秒數是30秒
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/6735a766-8dac-45b4-ba19-6c6fca4837d8)
- 6.範例兩階段驗證登入，https://appleid.apple.com，在這裡可以使用Guide(燈泡圖示)>選擇SING IN，這些步驟是要使用者自行操作，所以後續到Sign UP之前的步驟刪除掉

## Email Automation
## DOCX/PPT Automation
## Google Sheets Automation
## Automation Trigger
## EXCEL Automation
## PDF Automation
## Desktop Automation
## Archieve Automation
## LIB



