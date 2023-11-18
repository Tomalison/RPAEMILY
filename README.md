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



