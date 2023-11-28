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
- 7.更改技能，選該技能，按下設定，就可以改裡面的內容，群組可以把技能的狀態放在一起，例如YT登入技能、YT搜尋技能，可以用成combo
- 8.Reset Broswer可以清除瀏覽器快取，這樣確保流程都可以一致；Allow group users modify允許群組成員更改技能
- 一個技能只能有一個循環工作
- 10.使用新瀏覽器執行子技能，會再開一個新的Emily瀏覽器，就可已達到循環中還有循環的功能

## Web Script
### document 物件獲取網頁元素的方法
- document.getElementByID('dd["data-type="24hr"]') //屬性選取器
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/492bfe2b-abf3-4f06-a0f9-3a24369723b0)
- document.querySelectorAll(".col3f") = document.querySelectorAll('dl["class="col3f"]') 
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/3ec4c711-6670-4381-bec7-1e5d36908d83)
- 先找到你要的網頁元素
``` sh
獲取符合條件的第一個網頁元素 :
document.getElementById() 透過 #id 獲取網頁元素
document.querySelector()
獲取多個符合條件的網頁元素
document.getElementsByClassName() 根據 css 類別獲取網頁元素
document.getElementsByTagName() 根據標籤名稱獲取網頁元素
document.querySelectorAll()
```
- 所以當HTML可以找到你要的元素後，就可以用javascripts去控制
``` sh
let searchBox = document.querySelector("#keyword"); //輸入框
let searchBtn = document.querySelector("#btn_search"); // 搜尋鈕
searchBox.value = "iPad"; //輸入框輸入文字
searchBtn.click(); //點擊搜尋鈕  
```
- 雲中台篩選日期控制為昨日的範例
``` sh
var inputElement = document.querySelectorAll('div[widgetname="PARA_BDATE2"] input[type="text"]')[0];
if (inputElement) {
    inputElement.value = formattedDate;
}
```
- 搜尋結果標題與價格
``` sh
使用開發人員工具找到 :
當前頁面所有搜尋結果的標題
當前頁面所有搜尋結果的價格
參考程式碼 
document.querySelectorAll(".prod_name"); //商品標題
document.querySelectorAll("span.price > span.value"); // 商品價格 在子節點
//打印第一個商品標題的文字
console.log(document.querySelectorAll(".prod_name")[0].innerText)
```
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/5ef6faf6-8ab8-450b-892b-fe0d30ff1656)
- 捲動至最後一筆搜尋結果 (目的是他是拉下去時，才會load更多結果)
``` sh
參考程式碼 :
let lastItem = document.querySelectorAll(".prod_name")[19]; //最後一個商品標題
lastItem.scrollIntoView({block : "center"});
//再次練習 7-3
document.querySelectorAll(".prod_name"); //商品標題
```
### 執行腳本程式碼編輯
- 設定完節點路徑後，EMILY 會根據該路徑找到相關的節點，並存為 nodes 變數，可於程式碼編輯區操作。console.log(nodes)

- 執行腳本有提供 :
- lodash 套件
- moment 套件
- 常用函式
- read(filename); //讀取文字檔
- write(filename, text); //寫出文字檔
- remove(filename); //移除檔案
- repeat(boolean, delay); //重複執行腳本
https://classroom.google.com/u/1/c/NjE5NzQxNDgzNzM0/m/NjE5NzQxNDgzNzg4/details
- 範例，執行腳本查PCHOME商品資訊

-輸入關鍵字並提交
``` sh
參考程式碼 :
let keyword = read("row-keyword.txt"); //讀取文字檔內容
let searchBox = document.querySelector("#keyword"); //輸入框
let searchBtn = document.querySelector("#btn_search"); // 搜尋鈕
searchBox.value = keyword; //輸入關鍵字
searchBtn.click(); //點擊搜尋鈕
```

- 輸入價格範圍，並再次提交
``` sh
參考程式碼 :
let min_price = read("row-min_price.txt"); //最小值
let max_price = read("row-max_price.txt"); //最大值
let minNode = document.querySelector("input#MinPrice"); //最小值輸入框
minNode.value = min_price;
let maxNode = document.querySelector("input#MaxPrice"); // 最大值輸入框
maxNode.value = max_price;
let searchNode = document.querySelector("input#btn_PRC"); // 搜尋按鈕
searchNode.click(); // 點擊搜尋鈕
```

- 捲動至頁面最底部程式碼撰寫邏輯
``` sh
程式碼撰寫邏輯 : 利用 repeat() 不停執行腳本，直到捲動至頁面最底部
let previousNum = 讀取上次搜尋結果數量;
let currentNum = 紀錄當前搜尋結果數量;
//將當前搜尋結果數量寫出成文字檔，提供下次執行此腳本時使用
write("previousNum.txt", JSON.stringify(currentNum));
捲動頁面;
if(currentNum > previousNum) repeat();
``` 
- 捲動頁面至底部
``` sh
參考程式碼 :
let previousNum; // 初始化 previousNum 變數
try{ // try…catch(e)... 會嘗試執行下方程式碼，若出現錯誤，則執行 catch 程式碼
previousNum = Number(read("previousNum.txt")); // 讀取 previousNum 文字檔內容，為上次執行時的紀錄
}catch(e){
previousNum = 0; // 第一次執行時，工作資料夾中沒有 previousNum.txt 可讀取，故初始化數值為 0
}
let items = Array.from(document.querySelectorAll("div#ItemContainer > dl")); //抓取每一筆搜尋結果，並轉為陣列
let currentNum = items.length; // 當前搜尋結果數量 = 陣列長度
write("previousNum.txt", JSON.stringify(currentNum)); //寫出當前數量，提供下次執行時比對
_.last(items).scrollIntoView({block : "center"}); //利用 _.last() 抓取最後一筆搜尋結果，並捲動畫面至該筆結果
if(currentNum > previousNum) repeat(); //比對 currentNum 與 previousNum，若數量不一致則重複執行此腳本
``` 
- 執行腳本 : 抓取商品資訊
``` sh
參考程式碼 :
let items = Array.from(document.querySelectorAll("div#ItemContainer > dl")); //抓取每一筆搜尋結果，並轉為陣列
let itemInfo = []; //初始化商品資訊陣列
items.forEach(item => {
product_name = item.querySelector("h5.prod_name"); //抓取該節點的商品名
product_price = item.querySelector("span.price > span.value"); //抓取該節點的商品價格
itemInfo.push({
"product_name" : product_name.innerText, //輸出節點內文為商品名稱
"price" : product_price.innerText //輸出節點內文為商品價格
})
})
write("itemInfo.txt", JSON.stringify(itemInfo)); //寫出抓取結果
remove("previousNum.txt"); //刪除本次的數量紀錄，避免影響到下一次的循環工作
``` 
- 執行腳本開發建議
``` sh
開發之前，請用瀏覽器的開發者工具觀察、嘗試操作該節點

有些節點上的 attribute屬性 是動態產生，例如 : 每次造訪網頁頁面時，同一個節
點的 id 會變動，沒有辦法依靠特定 attribute屬性來找到正確節點，這部分需要對
網頁的節點作觀察並制定找到正確目標的方法。

撰寫腳本之前，請打印 console.log(nodes) ，查看設定的節點路徑是否精準
每一次的腳本執行只操作當前頁面
```
- 用chatgpt 在+上去找要找的位置
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/e68cb4ea-d682-451a-b873-f7e3f66f0b44)

## Google Sheets Automation
- 要RPA操作google sheet要先做前置作業>goolge cloud plamform> 搜尋google sheet api> 建立憑證 > 服務帳戶 > 點擊金鑰(新增金鑰(建立)) > JSON檔 > 點擊EMILY帳號設定 放下金鑰 _設定完成
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/2aa817d8-9b58-4f7a-85df-c581df8525e6)
- 回到google sheet 中間是sheet id > 將表單先共享給emily-548@tokyo-unity-280609.iam.gserviceaccount.com這個郵箱 > 回到RPA訓練模組，選擇google sheets技能模組> 將要控制的表單ID放到 Spreadsheet ID > 輸入 console.log(api.sheetNames()) 可以確認表單的工作表
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/21c11ac5-b49f-4ecd-b0e6-0226546cb6fd)
### 同步函式 : 
- api.sheetNames(); //取得所有工作表名稱
### 非同步函式 : 
- await api.addSheet(header, rows, name); //新增工作表並填入表頭與資料
- await api.delSheet(name); //刪除工作表
- await api.addRows(name, rows); //新增多列資料至指定工作表
- await api.delRow(name, rowIndex); //刪除工作表某列資料
- await api.getCell(name, rowIndex, columnIndex); //取得特定儲存格值 rowIndex =0~, columnIndex = A~Z
- await api.setCell(name, rowIndex, columnIndex, value); //寫入值至特定儲存格
測試google : https://docs.google.com/spreadsheets/d/19kiDcEi5kZvviyU2c3gdB2O7X-U5ITefOmYkX8PkKxw/edit#gid=1200849655
https://theoephraim.github.io/node-google-spreadsheet/#/classes/google-spreadsheet-worksheet
``` sh
console.log(api.sheetNames())
await api.setCell('new sheet', 3, 0, 'Tom')
```
``` sh
console.log(api.sheetNames())
let sheet = await api.loadSheet('new sheet', 'A1:E5')
let cell1 = await sheet.cell(3,0)
cell1.value = 'Jerry'

let cell2 = await sheet.cell(3,1)
cell2.value = 'advertise'
await sheet.save()
```
``` sh
let employeeInfo = await input.sheetsByTitle["new sheet"].getRows(); //取得工作表中表格資料
let bobInfo = _.find(employeeInfo, (row)=> row["name"] == "Jerry"); //篩選表格資料 name = "Jerry"
bobInfo["department"] = "accounting"; //將 name = "Jerry" 的列資料，department 欄位改為 "accounting"
await bobInfo.save(); //儲存修改的內容
```
``` sh
let buffer = await input.sheetsByTitle["員工資訊"].downloadAsCSV(false); //將工作表內容存為 buffer
api.write("test.csv", buffer); //寫出檔案
```
- 組合技 結束 > 先插入新指令，用Excel分析資料，PICK檔案 > 然後回到googlesheet的自動化處理單元，點下調整參數 
- 插入指令
``` sh
console.log(input)
output['品類銷售匯總'] = JSON.stringify(input)
```
- 回到自動化處理單元
``` sh
console.log(input)
let productsell = JSON.parse(api.read("品類銷售匯總.txt"))
let header = ['門店編號',	'門店名稱',	'營業日期',	'班次',	'上級分類名稱',	'分類名稱',	'系列',	'商品編號',	'商品名稱',	'商品特徵',	'銷售數量',	'應售金額',	'折扣金額',	'實銷金額',	'未稅金額'	,'商品銷售單數'	,'客單價'	,'客件數'	,'銷售金額占比']
// console.log(productsell)
await api.addSheet(header, productsell, 'new sheet')
await api.addRows('new sheet', productsell)
```
``` sh

```
### api控制表單
- api.addSheet(header, rows, name)
- header表頭
- rows列以object的形式
- name創建新表格的名稱
``` sh
let header = ['Name', 'department']
let rows = [
{'Name':'Alice','department':'accounting'},
{'Name':'Bob','department':'marketing'}
]
await api.addSheet(header, rows, 'new sheet')
``` 
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/97fada17-765d-4b6b-8ab6-21c8ffdd180d)
- java-ctrl+/可以同步註解
- 刪除表單方式:
``` sh
api.delSheet('工作表1')
```
- 新增欄位資料方式，要用addRows
``` sh
let rows2 = [
{'Name':'Candy','department':'marketing'},
]
await api.addRows('new sheet', rows2)
```
- 透過api取出資料
``` sh
let data = await api.getRows('new sheet')
console.log(data)
```
- 刪除某一列的資料 (這裡不包含表頭，所以開始算由第二列開始 0-1-2 跟python一樣)
``` sh
await api.delRow('new sheet', 2)
```
- 控制某一個欄位
``` sh
let cell = await api.getCell('new sheet', 2, 1)
console.log(cell)
```
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/a3c1ad81-5c49-4836-81ec-6dd716fce991)
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/16e7272c-a28e-4db6-9fbe-359c8e5f7dcc)
- 抓到那個欄位後，更改欄位內容
``` sh
await api.setCell('new sheet', 2, 1, 'advertise')
```
## EXCEL Automation 
### Excel 表格處理
- 先開啟dubug>切換到console頁面 > PICK你路徑中的xlsx檔 > 選擇你要分析的分頁 > 按下detect > 可以先console.log(input)查看資料是否都有進來了；(Header也可以改名稱) (A1就是第一列當表頭)
- 可以直接在Low code位置撰寫你要針對欄位調整的程式，如下範例，將某price欄位全部+成10%
``` sh
console.log(input)

input.forEach((row) => {
  output.push({
    name: row.name,
    price: row.price*1.1
  })
})
cosole.log()
```
- 如果只是要針對某幾個符合條件的price調整10%，例如price>100的，可以這樣寫
``` sh
let lowPriceProduct = _.filter(input, p => p.price < 100)

lowPriceProduct.forEach((row) => {
  output.push({
    name: row.name,
    price: row.price*1.1
  })
})
cosole.log()
```
- 如果要表頭欄位改名，可以向下圖
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/a2ceb965-a98d-45bd-8db2-15c84267474b)
- 另外一種方式，可以向下圖，依照col順序 : 0代表第一欄 ，以此類推
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/eb6f82a7-8b17-454b-9365-062e7f5f323d)
- 另外一種正規表示法，先尋找欄位，再把該物件欄位用成該名字，用這種方式可以針對EXCEL欄位名稱相同，但每次下載的欄位資料位置都不同
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/36f7e6fb-7197-4fcf-8e9d-365d56573337)

- output.push(input[0]) 可以將你選取的列轉換成CSV、XLSX檔
``` sh
let temp = [{"key1" : "value1"},{"key2" : "value2"}]
temp.forEach(row => output.push(row))
```
- 在Emily這個模組中 output這個變數已設定好只像電腦的記憶體A，而Emily在製作表格時會參考記憶體A上儲存的資料，但output = 會將output這個變數重新指向至記憶體B，但Emily還是根據記憶體A來製作表格。因此在輸出的時候，不能將output重新assign
``` sh
console.log(input)
input.forEach( row => {
  
  if(row['門店編號']==='ZA001'){output.push(row)}
})
```
- 先放入長度，在定義長度為0清空資訊

``` sh
console.log(input.length)

output.length = 0
input.forEach( row => {
  
  if(row['門店編號']==='ZA001'){output.push(row)}
})
```

### Excel 表格分析
- 先開啟dubug>切換到console頁面 > PICK你路徑中的xlsx檔 > 選擇你要分析的分頁 > 按下detect > 可以先console.log(input)查看資料是否都有進來了
- 抓進來之後，我們可以分析資料的內容，例如我要找出銷售金額最高的資料，那因為資料是從第二列開始，Data Cell要從A2開始


``` sh
console.log(input)
output['maxPrice'] = _.maxBy(input, '實銷金額').實銷金額
console.log(output)
```
``` sh
console.log(input)
output['maxPrice'] = _.maxBy(input, '實銷金額').實銷金額
console.log(output)
```

- 以下可以將程式碼寫完計算後，會變成txt檔，這時候要Save起來，再用Navigate(首頁)，CSV CREATOR將這個檔案產出
``` sh
console.log(input) //讀取資料夾中的txt檔
console.log(input['檔名']) //選擇資料夾中的txt檔
```
``` sh
console.log(JSON.parse(input['檔名'])) // 還原字串資料成excel
```
``` sh
let max = JSON.parse(input['檔名']) // 建立一個變數，存取還原字串資料的excel
console.log(max)
output.push(max)
```
![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/55643c87-0593-4166-aa1b-418cf3d94a5f)

``` sh
let productSummary ={}
productSummary['max Price'] = _.maxBy(input, '實銷金額').實銷金額
productSummary['min Price'] = _.minBy(input, '實銷金額').實銷金額
productSummary['mean Price'] = _.meanBy(input, '實銷金額')
output['productSummary'] = JSON.stringify(productSummary)
console.log(productSummary)
```
- 再用Navigate(首頁)，CSV表格建立將這個檔案產出，Output filename取檔名即可
``` sh
let productSummary = JSON.parse(input['productSummary'])
output.push({
  'Max price': productSummary['max price'],
  'Min price': productSummary['min price'],
  'Mean price': productSummary['mean price']
})
```

https://docs.emily.tips/excel2txt

``` sh
console.log(input)
output['檔名'] = JSON.stringify(input) //字串化資料
console.log(output)
```
``` sh
console.log(input)
let max = _.maxBy(input,"實銷金額")
console.log(max)
output['最高銷售金額'] = JSON.stringify(max)
```
### Excel 輸出
- 開啟Writer之後，先用程式碼確認是否可正常讀取分頁
``` sh
console.log(api.sheetNames())
```
- getCell代表的是指取該欄位的欄位值，第一個參數放表單名稱，後兩個參數放欄位位置，0,1代表B1欄位 /  0,2代表C1欄位 / 0, 0代表A1欄位 / 1, 0代表A2欄位 以此類推
``` sh
console.log(api.getCell(api.sheetNames()[0], 0, 1]
console.log(api.getCell(api.sheetNames()[0], 0, 2]
```
- 先透過getCell取資料、分割資料；再用setCell分別填入資料欄位
``` sh
let sName = api.sheetNames()[0]

let fNameOne = api.getCell(api.sheetNames()[0], 0, 1).split(' ')[0]
let lNameOne = api.getCell(api.sheetNames()[0], 0, 1).split(' ')[1]

let fNameTwo = api.getCell(api.sheetNames()[0], 0, 2).split(' ')[0]
let lNameTwo = api.getCell(api.sheetNames()[0], 0, 2).split(' ')[1]

api.setCell(sName, 0 , 0, 'first name')
api.setCell(sName, 0 , 1, 'last name')
api.setCell(sName, 1 , 0, 'fNameOne')
api.setCell(sName, 1 , 1, 'lNameOne')
api.setCell(sName, 2 , 0, 'fNameTwo')
api.setCell(sName, 2 , 1, 'fNameTwo')
api.setCell(sName, 0 , 2, '')
```
- 也可以用以下內容更改EXCEL的外觀，接著指要在setCell後面篩入style就可以指定欄位外觀api.setCell(sName, 0 , 0, 'first name', style)
``` sh
const style  {
  alignment:{
    vertical: 'top',
    horizontal: 'center',
    wrapText: false,
},
font: {
  name: 'Calibri',
  sz: '14',
  color: {rgb: '556B2F'},
  bold: true,
  italic: true,
  underline: false,
  strike: false,
  }
}

```
## Email Automation
- 
## DOCX/PPT Automation


## Automation Trigger (排程)

## PDF Automation

## Desktop Automation
- 桌面自動化: 模擬人操作電腦的行為，將螢幕、滑鼠、鍵盤交給 EMILY.RPA 操作
- OPEN TRAINER UI : 打開開發介面
- DA 模組會模擬人眼看螢幕、手使用鍵盤與滑鼠來自動化的操作
- 我們將會使用相關的 API 指令來操作電腦的每一個步驟
- 開發時，要告訴 EMILY 去辨認當前螢幕畫面的哪個地方是需要操作的
- 我們在開發介面上可以使用螢幕快照功能，並操作訓練介面來告訴 EMILY 應該
- 要辨識出當前螢幕畫面的哪個圖案，並使用鍵盤或滑鼠來操作
- 先點下快門>no code螢幕圖示 > 接著可以在這個圖片做你要的指令動作，也可以再撥放鍵旁的圖片集找
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/aa1158c8-3cfb-4956-ba5d-bbe854b0fed8)
- Trial按下commit之後可以進到final區>在按下commit就會搬到low code
- ![image](https://github.com/Tomalison/RPAEMILY/assets/96727036/40480171-b53e-4b08-ac8b-2bc7e8132482)
``` sh
TRIAL : 目前實驗用程式碼
FINAL : 完整程式碼編輯區
Commit : 輸出當前面板程式碼至工作資料夾與 EMILY 模組
Run Code : 測試當前面板程式碼，並更新螢幕畫面截圖
Abort : 中斷當前執行的程式碼
```
- 圖片辨識很容易失敗，可以用MASK-Crop > 然後可以用crop-xy點擊圈選位置的周邊(座標)
``` sh
螢幕相關
    await api.screen.whatToDo()
滑鼠相關
    await api.mouse.whatToDo()
鍵盤相關
    await api.keyboard.whatToDo()
剪貼簿相關
    api.clipboard.whatToDo()
    shell 相關
    await api.shell.whatToDo()
其他常用
    較常見用到的組合功能
    例如 : ctrl + C

螢幕操作 api.screen
搜尋截圖位置
    let pic1 = await api.screen.find("截圖檔名")
    console.log(pic1)
等待截圖出現
    await api.screen.waitFor("截圖檔名", n)
    *等待截圖出現，最多等待 n 毫秒(ms)

滑鼠游標操作 api.mouse
左鍵/右鍵點擊
	await api.mouse.clickLeft()
	await api.mouse.clickRight()
移動游標
	await api.mouse.move(x, y)
游標拖曳
	await api.mouse.drag(x, y)
	*將滑鼠游標從現在位置拖曳至 (x, y)
滾輪滑動(上/下/左/右)
	await api.mouse.scrollUp(n)
	await api.mouse.scrollDown(n)
	await api.mouse.scrollLeft(n)
	await api.mouse.scrollRight(n)

鍵盤操作 api.keyboard
文字輸入/組合鍵輸入
	await api.keyboard.type(text)
	await api.keyboard.type(api.key.LeftControl, api.key.A)
*組合鍵 : ctrl + A，鍵盤的按鍵表示請參考線上文件 https://docs.emily.tips/da
功能鍵輸入
	await api.keyboard.enter()
	await api.keyboard.escape()
	await api.keyboard.backspace()
	await api.keyboard.tab()

剪貼簿操作 api.clipboard
寫入剪貼簿
       api.clipboard.writeText(text)
讀取剪貼簿
	let str1 = api.clipboard.readText()
	console.log(str1)

檔案系統操作 api.shell
開啟檔案(工作資料夾中檔案/絕對路徑檔案)
	await api.shell.openPath("output.csv")
	await api.shell.openPath("C:\Users\Desktop\output.csv")
開啟檔案總管並選取檔案
	await api.shell.showItemInFolder("C:\Users\Desktop\output.csv")
開啟預設瀏覽器並前往網址
        await api.shell.openExternal("https://google.com")
檔案移至資源回收桶
	await api.shell.trashItem("C:\Users\Desktop\output.csv")

其他常用 API
點擊截圖
	await api.clickCrop("截圖檔名")
移動游標至截圖
	await api.moveToCrop("截圖檔名")
貼上指定文字
	await api.pasteText(text)
讀/寫 CSV 檔
	let table = await api.readCSV("test.csv", ",", 0) 
*讀取 test.csv，逗號分割，忽略 0 列(第一列為表頭)
	await api.writeCSV("output.csv", table)
常見組合鍵
	await api.ctrlC()
	await api.ctrlV()
	await api.ctrlA()
等待數秒
	await api.sleep(n)

在使用 DA 模組進行自動化時，由於 EMILY 會比對當初的截圖與當前的螢幕畫面，並且占用該電腦的鍵盤與滑鼠，所以會有以下限制 : 
螢幕解析度、標的物的樣子不能變動，否則 EMILY 可能會比對不到相對應的標的物，而造成自動化失敗。
在 DA 自動化運行中，該電腦不能再使用其他操作，否則可能導致自動化流程失敗。
操作的軟體若有版本/介面的更新，要注意是否會影響自動化
使用者要確保輸入法的狀態。有時系統對於某些應用程式會自動切換輸入法，而 EMILY 是真的根據所給內容按下鍵盤，可能會造成輸入的資訊錯誤

```
- Move to crop 移動滑鼠
- Capture to OCR 只能辨識英文跟數字
- INPUT Text : use keyboard/會有輸入法的受限 ；use clipboard(剪貼簿的方式/比較不會有剪貼簿的受限
- Send Key(S) : 可以組合你常見的按鍵 例如ctrl+A全選
- Sleep : 操作要等待，可以讓Emily等待幾秒
- Copy XY: 複製你當前滑鼠的位置座標
- Click Left / Right: 滑鼠左右鍵點擊
https://classroom.google.com/u/1/c/NjE5NzQxNDgzNzM0/m/NjE5NzQxNDgzNzgz/details
``` sh
截圖小常識
在 ALL CROPS 介面中的截圖，會存檔於工作資料夾 tmp 中，若於 ALL CROPS
介面中刪除，tmp 中該圖片亦會刪除
若開發前 tmp 中已有截圖，在『開發DA新技能』或『調整』舊有DA技能時，會將
tmp 中截圖一併放置於 ALL CROPS 中
SAVE 流程時，會將 tmp 中圖片一併儲存
『調整』DA 模組時，會將該 DA 技能中所儲存的截圖下載至 tmp 中
『執行』DA 模組時，會將該 DA 技能中所儲存的截圖下載至流水號資料夾中
DA 中的截圖檔名通常難以辨別該圖片的內容，所以在截圖取得檔名後，建議在程式
碼最一開始宣告一個物件來存放檔名
物件 key-value 建議對應的方式為 "圖片描述" : "圖片檔名"
例如在程式碼開頭宣告 :
let crops =
{ "add" : "crop-1198550763b6611ea66f20f5d02ad6920b6209bb5a01691e2a28d7fc7fced956.png",
"number1" : "crop-9acaca2b92257f1f566549d4ef0e3c67c10087feec0c92f21baf89dcb283d760.png" }
在程式碼中需要用到的時候就可以直接進行取用，例如 :
await api.clickCrop(crops["number1"], 15, 20);
await api.moveToCrop(crops["add"]);

常用的操作寫成 function
在 DA 模組中我們會把每個動作化作一行一行的指令，若有常用的動作，建議將這些
動作合併為一個 function
例如 : 我將『clickCrop』、『Ctrl + C』合併為『clickCropAndCopy』函式如下 :
async function clickCropAndCopy(cropName){
await api.clickCrop(cropName);
await api.ctrlC();
}
後續若我有使用到這樣的功能，我可以直接呼叫
await api.clickCropAndCopy(crops["number1"]);
這行程式碼就會執行『clickCrop』、『Ctrl + C』

TRIAL/FINAL 程式碼編輯
DA 開發時會按照操作順序來編寫程式，若有一小段程式碼需要做測試，我們會將該
段程式碼撰寫於 TRIAL 面板測試，並將測試過的程式碼段落整理至 FINAL 面板。因
此在整個 DA 模組開發完畢時，完整的程式碼就會整理在 FINAL 面板。

適時使用 COMMIT 儲存程式碼
在 DA 開發介面中，COMMIT 功能可以將當前面板的程式碼提交回 EMILY 中，同時
亦會在工作資料夾 tmp 中儲存程式碼的 Javascript 檔案，檔名如 : code-final-xxx.js或
是 code-trail-xxx.js，建議程式碼編輯到一個段落時，都使用 COMMIT 將程式碼儲存
於 tmp 中
*若沒有儲存，且誤關了開發介面或是EMILY，將會流失已撰寫好的程式碼
```
``` sh
螢幕相關 API

取得螢幕大小 api.screen.size()
await api.screen.size();
說明 : 取得當前螢幕大小
參數 : 無
回傳 : (Object) 物件，當前螢幕大小
物件格式 : {"width":2256 , "height":1504}

搜尋截圖位置 api.screen.find()
await api.screen.find(filename, options);
說明 : 在當前畫面上找尋指定的截圖，並回傳該截圖在當前螢幕上的位置
參數 :
filename :(String) 字串，截圖檔名
options :(Object) 選項物件 ，控制項
回傳 : (Object)截圖位置物件
物件格式 : {"left":100 , "top":100, "height":50,"width":100, "confidence":0.9997}
{"left":100 , "top":100, "height":50,"width":100, "confidence":0.9997}

參數 : options 控制項物件
說明 : 此參數可以控制搜尋圖片的範圍與最低信心水準
格式 :
{"left":0 , "top":600, "height":300,"width":300, "confidence":0.98}
說明 :
"left" : 與螢幕左界的距離(pixel)
"top" : 與螢幕上界的距離(pixel)
"height" : 高度(pixel)
"width" : 寬度(pixel)
"confidence" : 信心水準(0~1)

等待截圖 api.screen.waitFor()
await api.screen.waitFor(filename, millisecond, options);
說明 : 在當前畫面上等待指定的截圖，在等待最大秒數內出現該截圖後才會執行下一
行指令，並回傳該截圖在當前螢幕上的位置，若在設定的秒數內沒有找到該截圖，則
會報錯
參數 :
filename :(String) 字串，截圖檔名
millisecond :(Num) 數字 ，等待毫秒數
options : (Object) 物件，控制項
回傳 : (Object) 截圖位置物件
物件格式 : {"left":100 , "top":100, "height":30,"width":30, "confidence":0.9997}

```
``` sh
滑鼠相關 API

操作滑鼠移動/拖拉/點擊
await api.mouse.move(x, y);
說明 : 移動滑鼠至指定座標
參數 :
x :(Num) 數字，當前螢幕 x 座標 (pixel)
y :(Num) 數字，當前螢幕 y 座標 (pixel)
await api.mouse.clickLeft();
說明 : 點擊左鍵
await api.mouse.drag(x, y);
說明 : 拖拉滑鼠至指定座標
參數 :
x :(Num) 數字，當前螢幕 x 座標 (pixel)
y :(Num) 數字，當前螢幕 y 座標 (pixel)
await api.mouse.clickRight();
說明 : 點擊右鍵

滑鼠滾輪操作
await api.mouse.scrollUp(n);
await api.mouse.scrollDown(n);
await api.mouse.scrollLeft(n);
await api.mouse.scrollRight(n);
說明 : 使用滑鼠滾輪向(上/下/左/右)捲動
參數 :
n :(Number) 數字，滾輪滾動數，該台電腦的滾輪設定會影響捲動的幅度
```

``` sh
鍵盤相關 API

文字輸入/按鍵輸入 api.keyboard.type()
await api.keyboard.type(text);
說明 : 使用鍵盤輸入文字，EMILY會使用電腦當前輸入法一一輸入文字
參數 :
text : (String) 字串，要輸入的文字
await api.keyboard.type(key1, key2, …);
說明 : 使用鍵盤依序按下按鍵，可使用組合鍵
參數 :
key : 按鍵碼，如 api.key.LeftControl，按鍵表參考下頁

參數 : 按鍵碼 api.key
說明 : 使用 await api.keyboard.type(key1, key2, …); 中的按鍵碼參數，提供的按鍵碼
如下
註 :
Super 鍵 = Windows Win鍵
= Mac Command鍵

功能鍵輸入
await api.keyboard.enter();
await api.keyboard.escape();
await api.keyboard.backspace();
await api.keyboard.tab();
說明 : 按下功能鍵 Enter/Esc/Backspace/Tab
```
``` sh
剪貼簿相關 API

api.clipboard.write()/api.clipboard.read()
api.clipboard.write(text);
說明 : 將文字內容寫入系統剪貼簿中
參數 :
text : (String) 字串，要寫入的文字
api.clipboard.read();
說明 : 讀取系統剪貼簿中文字
回傳 : (String) 字串，系統剪貼簿中文字

```
``` sh
檔案系統相關 API

開啟檔案 api.shell.openPath()
await api.shell.openPath(path);
說明 : 開啟指定路徑的檔案
參數 :
path : (String) 字串，檔案/應用程式的路徑
*註 : 若要開啟工作資料夾中的檔案，直接給檔案的名稱即可，例如 :
await api.shell.openPath("text.xlsx"); // 開啟工作資料夾中的 test.xlsx 檔案

開啟檔案位置並選取 api.shell.showItemInFolder()
await api.shell.showItemInFolder(path);
說明 : 開啟該檔案所在位置的資料夾，並選取該檔案
參數 :
path : (String) 字串，檔案/應用程式的路徑

檔案移至資源回收桶 api.shell.trashItem()
await api.shell.trashItem(path);
說明 : 將指定路徑的檔案移至資源回收桶
參數 :
path : (String) 字串，檔案/應用程式的路徑

開啟網頁連結 api.shell.openExternal()
await api.shell.openExternal(url);
說明 : 呼叫預設瀏覽器，並前往指定網頁
參數 :
url : (String) 字串，網址
```

``` sh
其他實用 API

移動滑鼠至截圖 api.moveToCrop()
await api.moveToCrop(filename, relX, relY, options);
說明 : 移動滑鼠至指定截圖
參數 :
filename :(String) 字串，截圖檔名
relX :(Num) 數字，相對座標 X
relY :(Num) 數字，相對座標 Y
options :(Object) 選項物件 ，控制項
註 : 此 API 相當於 api.screen.find() + api.mouse.move()

點擊截圖 api.clickCrop()
await api.clickCrop(filename, relX, relY, options);
說明 : 移動滑鼠至指定截圖並點擊
參數 :
filename :(String) 字串，截圖檔名
relX :(Num) 數字，相對座標 X
relY :(Num) 數字，相對座標 Y
options :(Object) 選項物件 ，控制項
註 : 此 API 相當於 api.screen.find() + api.mouse.move() + api.mouse.clickLeft()

貼上文字 api.pasteText()
await api.pasteText(text);
說明 : 在當前輸入框貼上指定文字
參數 :
text :(String) 字串，文字
註 : 此 API 相當於
api.clipboard.write(text) + api.keyboard.type(api.key.LeftControl, api.key.V)

全選/複製/貼上
await api.ctrlA();
說明 : 全選
註 : 此 API 相當於 api.keyboard.type(api.key.LeftControl, api.key.A);
await api.ctrlC();
說明 : 複製
註 : 此 API 相當於 api.keyboard.type(api.key.LeftControl, api.key.C);
await api.ctrlV();
說明 : 貼上
註 : 此 API 相當於 api.keyboard.type(api.key.LeftControl, api.key.V);

時間暫停 api.sleep()
await api.sleep(n);
說明 : 暫停幾秒鐘
參數 :
n :(Num) 數字，毫秒
註 : 此 API 常用於各項動作的指令之間，避免 EMILY 執行太快速，電腦速度跟不上

讀取 CSV 檔 api.readCSV()
await api.readCSV(filepath, separator, headerRow);
說明 : 讀取 CSV 檔案
參數 :
filepath :(String) 字串，CSV 檔案路徑，或是工作資料夾中檔名
separator :(String) 字串，檔案以什麼符號分割，通常為逗號 ","
headerRow :(Num) 數字，表頭列位置的列數，0 代表第一列
回傳 : (Array) 陣列，物件陣列表格資料
格式 : [{"header1" : 10, "header2" : 20}, {"header1" : 15, "header2" : 6}, …]

寫出 CSV 檔 api.writeCSV()
await api.writeCSV(filename, data);
說明 : 寫出 CSV 檔案
參數 :
filename :(String) 字串，CSV 檔名
data :(Array) 陣列，物件陣列表格資料
格式 : [{"header1" : 10, "header2" : 20}, {"header1" : 15, "header2" : 6}, …]

```

``` sh
常用操作 : 重複執行一系列動作

說明 : 同樣的動作要執行多次，可以利用迴圈來執行，例如 : 執行 5 次移動滑鼠

參考程式碼 :
for(let i = 0; i<5; i++){
await api.mouse.move(0, 0);
await api.sleep(1000);
await api.mouse.move(150, 150);
await api.sleep(1000);
}
註 : 非同步程式碼不能使用 Array.forEach() 來執行，但是 for、while 等 loop 可以

常用操作 : 捲動頁面直到指定截圖出現
說明 : 模擬人使用滑鼠捲動頁面，看見指定目標後進行後續的操作
參考程式碼 :
let conf = 0; // 起始 confidence 值
while(conf < 0.99){ //圖片 confidence < 0.99 要繼續找、捲動，直到 >0.99為止
let result = await api.screen.find("targetPic"); // 搜尋目標圖片
await api.mouse.scrollDown(300); // 向下捲動
conf = result.confidence; // 更新 conf 數值，為本次搜尋結果的 confidence
}

DA 常見除錯處理
Q : EMILY DA 執行/測試有問題，該朝哪個方向做調整 ?
螢幕相關指令 :
MASK 圖片留下要辨識的部分，提高精確度
調高選項物件 confidence (預設為 0.95)，例如調整至 0.99，找出高相似度的圖
調整選項物件，限制圖片搜索區域
滑鼠、鍵盤相關指令 :
輸入文字要確認輸入法，或是使用 await api.pasteText(text); 取代
其他 :
注意每個指令之間是否動作太快，適度的在指令之間加上 await api.sleep(n);

```
## Archieve Automation

## LIB

## Workspace Script (工作資料夾執行腳本)
- 於工作資料夾中執行 Low-Code，用以存取資料夾內的文字類檔案
### input輸入物件
- 在腳本中可以直接存取 input 內建物件。input 物件中的每個 key 為工作資料夾中的一個 TXT 檔案名稱（不包含副檔名），每個 value 為該檔案的文字內容，在腳本被執行時就會自動載入所有文檔，免去於腳本中自行讀取的麻煩：
``` sh
// 讀取工作資料夾中 price.txt 的值
let price = input['price']
console.log('price:', price)
```
### output輸出物件
- 當腳本需要輸出文檔時，可以直接修改 output 內建物件。加入 output 物件中的每個 key 將被輸出成工作資料夾中的一個 TXT 檔案，檔案名稱即為 key，文字內容為該 key 相對應的 value。
 ``` sh
// 寫入值到工作資料夾中 new_price.txt 
let new_price = 100
output['new_price'] = new_price
```
### api 物件
- 提供同步函式：api.files(), api.stat(filename), api.read(filename, encoding='utf8'), api.write(filename, text), api.rename(oldname, newname), api.remove(filename)。另外 moment.js 與 lodash 都是內建函式庫，可以直接使用：
 ``` sh
// 一筆筆列出所有工作資料夾中的檔案
api.files().forEach((file) => console.log(file))

// 讀取檔案的各類時戳資訊，例如檔案建立時間、修改時間、最近存取時間
console.log(api.stat('price.txt'))

// 讀取工作資料夾中的文字檔 price.txt
console.log(api.read('price.txt'))

// 寫出文字檔到工作資料夾中
api.write('time.txt', moment().format('HH:mm:ss'))

// 修改工作資料夾中的檔案名稱
api.rename('time.txt', 'currentTime.txt')

// 刪除工作資料夾中的檔案
api.remove('price.txt')
```
- 以及非同步函式，回傳 Promise 物件：api.run(uuid), api.readCSV(filename, separator, skiplines), api.splitCSV(filename, separator, skiplines, newname, maxRows), api.writeCSV(filename, rows, header) 與 api.writeXML(filename, obj, options)
 ``` sh
// 呼叫執行某個自動化技能，其識別碼為 ef4e12a6-636f-4e58-8e14-212089e6fd23
await api.run('ef4e12a6-636f-4e58-8e14-212089e6fd23')

// 將工作資料夾中的CSV格式大檔案分割成多個CSV格式小檔案，每個檔案不超過5000筆資料
let files = await api.splitCSV('large.csv', ',', 0, 'small.csv', 5000)

// 寫出的檔案：['small(0).csv', 'small(1).csv', ... ] 存成一個檔案列表
await api.writeCSV('list.csv', files.map((file, index) => {return {file, index}}), ['index','file'])

// 讀取工作資料夾中的CSV檔案並且印出資料
let list = await api.readCSV('list.csv')
console.log(list) 

// 將 JSON 物件轉換成XML格式並寫出檔案，其中<addr>加上屬性，輸出header並縮排
let obj = {
  root: [
    { date: '2023/03/12' },
    { item: 'coffee' },
    { item: 'tea' },
    {
      _name: 'addr',
      _content: '101F, #1, Taiwan Road',
      _attrs: {
        country: 'TWN',
        city: 'TPE'
      }
    }
  ]
}
await api.writeXML('result.xml', obj, { header: true, indent: '\t' })
```
- 另外也提供 zip 讀寫 API 以針對工作資料夾內的檔案做壓縮或解壓縮，此類 API 皆為非同步函式：
 ``` sh
// 讀取 input.zip 內檔案
let inputZip = api.zip()
await inputZip.load('input.zip')
let filesInZip = await inputZip.files()
filesInZip.forEach((file) => console.log(file))

// 解壓縮 input.zip 內的檔案 a.txt
await inputZip.extract('a.txt')

// 壓縮工作資料夾中 b.jpg 與 c.pdf 成 output.zip
let outputZip = api.zip()
await outputZip.add('b.jpg')
await outputZip.add('c.pdf')
await outputZip.save('output.zip')
```
- 切割CSV檔
 ``` sh
切割 CSV 檔 :
await api.splitCSV(filename, separator, skiplines, newname, maxRows); //await api.splitCSV('large.csv', ',', 0 , 'small.csv', 5000);
寫出 CSV 檔 : 
await api.writeCSV(filename, rows, header);
```

Lodash : https://lodash.com/docs/
_.find()
_.filter()
_.groupBy()
_.sumBy()
moment : https://momentjs.com/
moment('20220501').format("YYYY/MM/DD")
moment('20220501').add(1, 'day').format('YYYY-MM-DD')
moment('20220501').subtract(1, 'month')
