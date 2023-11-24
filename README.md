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
