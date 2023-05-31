# lunchsuggester
 ![image](https://github.com/ChihTsungLu/lunchsuggester/blob/main/Untitled.png)
[DEMO](https://chihtsunglu.github.io/lunchsuggester/?fbclid=IwAR1YrxvWWs-FNPZfwGPz47duew_WGwSwur3gU_53QPOQpLXlGfvhVhOld1w)
# 午餐選擇器
利用 Google Map 挑選附近的餐廳，可加入到「美食收藏」並利用輪盤隨機挑選收藏中的餐廳，解決「午餐不知道要吃什麼」的困擾

## **[Google Map API](https://developers.google.com/maps/documentation/javascript/load-maps-js-api)**
首先需要到[Google Cloud Console](https://console.cloud.google.com/)建立專案，啟用以下三種API服務及取得API KEY。
1. Places API：主要用於查詢地理位置相關的資訊，可獲取特定地點或地點集合的詳細資訊，例如地點的地址、類型、評價、評論等。
2. Maps JavaScript API：嵌入Google地圖，可根據自己的需求自定義地圖的外觀和功能。
3. Direction API：用於計算和顯示從一個地點到另一個地點的路線。可計算不同交通工具（如汽車、步行、自行車）的路線，並提供逐步的導航指示。

## **[Bootstrap框架](https://getbootstrap.com/)**
採用Bootstrap實作「美食收藏列表」，一個流行的前端開發框架，由Twitter團隊開發和維護。
Bootstrap 提供了一套CSS樣式和JavaScript組件，用於快速構建響應式網頁和網頁應用程式。
詳細使用說明及優缺點可參考：[連結](https://justnote.coderbridge.io/2022/03/06/bootstrap/)

## **localStorage**
將餐廳資料儲存至 Web browser，可以跨瀏覽器分頁做使用、使用者關掉分頁或瀏覽器再打開資料仍不會消失，且資料無期效限制，資料將永久被保留。
需要注意的地方：
localStorage 是使用鍵值對(key,value)的形式來存儲數據，但資料儲存若非字串，陣列或物件，會自動轉為字串(String)格式儲存。
因此
 1. JSON.stringify：將 array 資料"儲存"時轉為 JSON 格式的 string 型態，例如`localStorage.setItem('restaurantList',JSON.stringify(restaurantList));`
 2. JSON.stringify：將儲存資料"取回"轉為原先的資料型別，例如`const restaurantList = JSON.parse(localStorage.getItem('restaurantList')) || [];`

## **輪盤效果**
使用 [WhimWheel](http://dougtesting.net/winwheel/docs) 一個用於創建互動式轉盤的 JavaScript 函式庫
及 [GreenSock](https://greensock.com/get-started/) 控制動畫效果。
