# 8.2 MVC 與 HTML Template Engine

MVC 模式的全名是 Model-View-Controller，這是一種軟體架構。學習以 MVC 觀念，來重新製作 NoChat 用戶端網頁，很快就能體會到 MVC 的精神。MVC 中的 "V" 指的是 "View"，View 的意思是「可見」，也就是人類眼睛所能看到的畫面。

一般來看，這裡所指的 View 就是 Web UI 的部份；不過 View 也代表 Presentation（視覺），UI 與 Presentation 意義上並不完全相同。關於這點，後續討論 MVP 模式時，再另行說明。以下皆以 Presentation 來表示 Web UI，也就是 View 的部份。

MVC 的基本精神是將 Presenetation 與程式碼分開。Express 所產生的 *view/* 目錄就是用來存放 Presenetation，也就是 UI。將 UI 與程式碼切割，不助於維護良好的程式碼結構，讓程式設計人員將程式碼組織的更好。

MVC 的觀念在軟體工程裡非常重要，程式設計師可以透過 MVC 模式，讓程式碼的組識更好。有了 MVC 模式，整個專案的管理結構也會更好，例如：結構更好的目錄階層。

Express.js 是一個 MVC 的 Web Application 框架，要展現 MVC 模式的精神，首要的工作就是導入 Template 觀念，利用 Template 來撰寫 View（HTML5）。

### 學習 Jade 程式語言

HTML 的 Template 選擇很多，目前 Express.js 能支援的 Template Engine 有：

- hjs
- hbs
- Jade

Express.js 已經將 Jade 做為預設的 Template Egnine。Jade 的語法風格簡潔，而且易學。Jade 將會成為重要的 HTML Template Egnine，以及 HTML Template 程式語言。建議讀者儘量去先了解它的語法。

Jade 的語法非常容易學習，只要透過幾個基本的練習，就可以很快上手。以下以 3 個練習，介紹 Jade 程式語言的基本語法。關於 Jade 語法的完整說明，請參考：

http://jade-lang.com

![圖 8-2 Jade 是一個 Template Engine](../images/figure-8_2.png)

### Exercise 1：<h1> 大標題

接下來，說明如何在 Express.js 框架裡加入一個新的 HTML5 頁面。首先，先練習將以下的內容，改寫為 Jade，並放置於專案的 views/ 目錄下：

~~~~~~~~
<h1>Hello World!</h2>
~~~~~~~~

改寫為 Jade 語法：

~~~~~~~~
h1 Hello World!
~~~~~~~~

將上述內容儲存為 *views/hello.jade*。經由這個例子，可以知道 Jade 提供了一套很簡約的 HTML5 標籤語法。使用 Jade 來撰寫 HTML5 標籤，更不必擔心漏寫了結尾標籤，非常方便。

### Exercise 2：<p> 段落

如果要寫入一段文字的話呢？HTML5 利用 <p></p> 標籤來書寫段落文字：

~~~~~~~~
<h1>Hello World!</h2>
<p>這是一個文章段落。</p>
~~~~~~~~

改寫成 Jade 如下：

~~~~~~~~
h1 Hello World!
p 這是一個文章段落。
~~~~~~~~

Jade 的語法就是這麼簡單：只要懂得 HTML5 標籤語法，就可以很直接地將它改寫為 Jade。

### Exercise 3：完整的 HTML5 文件

一個標準的 HTML5 文件，需包含 *doctype*、*<html>* 標籤、*<body>* 標籤、*<head>* 區域等內容。這些同樣都可以用 Jade 來撰寫。

繼續修改 *hello.jade*，將它發展成完整的 HTML5 文件。

~~~~~~~~
1 doctype 5
2 html
3   head
4     title= title
5   body
6     h1 Hello World!
7     p 這是一個文章段落。
~~~~~~~~

![圖 8-3 *hello.jade* 輸出結果](../images/figure-8_3.png)

圖 8-3 是 *hello.jade* 的輸出結果，如果「檢視原始碼」的話，可以看到解析出來的 HTML5 內容：

~~~~~~~~
<!DOCTYPE html><html><head><title>學習 Jade</title></head><body><h1>Hello World!</h1><p>這是一個文章段落。</p></body></html>
~~~~~~~~

Express.js 預設會輸出最小化（Minify）後的 HTML5 文件內容。要如何使用瀏覽器來瀏覽 *hello.jade* 呢？這就是學習如何新增 URL Routing 的時候了。

---

Next: [8.3 解析 app.js](3-app.md)
