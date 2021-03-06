# 環境設定
## 安裝 Nodejs
  * 請到 Nodejs 官網 [https://nodejs.org/en/download/](https://nodejs.org/en/download/) 下載並安裝。

## 安裝編輯器
  * 推薦使用 [Visual Studio Code](https://code.visualstudio.com/) 或 [Sublime Text](https://www.sublimetext.com/)
## 註冊帳號
  * 到 [github](https://www.github.com) 註冊帳號
    * 如果是 Windows 系統安裝 [git-for-windows](https://git-for-windows.github.io/)
    * [git 教學](https://git-scm.com/book/zh-tw/v1/%E9%96%8B%E5%A7%8B)
  * 到 [heroku](https://www.heroku.com) 註冊帳號
  * 到 [facebook developers](https://developers.facebook.com) 申請成開發者帳號

# 建立簡易伺服器
## [Express](https://expressjs.com/) 
用來做後端伺服器的框架。範例檔案[連結](https://github.com/ntu-csie-train/chatbot-class/tree/master/examples/express)
```javascript
const express = require('express')
const app = express()

app.get('/', function (req, res) {
  res.send('Hello World!')
})

app.listen(3000, function () {
  console.log('Example app listening on port 3000!')
})
```

## [Request](https://github.com/request/request)
用來處理 HTTP 呼叫的套件。範例檔案[連結](https://github.com/ntu-csie-train/chatbot-class/tree/master/examples/request)
```javascript
const request = require('request')

let address = 'Taipei 101'
let url = `https://maps.googleapis.com/maps/api/geocode/json?address=${address}`

request(url,
  function (error, response, body) {
    console.log('error:', error) // Print the error if one occurred
    console.log('statusCode:', response && response.statusCode) // Print the response status code if a response was received
    console.log('body:', body) // Print the HTML for the Google homepage.
  })

```

## 部署 Facebook chatbot
  詳見這個[連結](./deploy_fb_chatbot.md)

## 部署 LINE
  * https://github.com/ntu-csie-train/line-echo-bot-starter
  * LINE Business Center https://business.line.me/
  * LINE API https://devdocs.line.me/en/#reply-message

## 部署 Telegram
  * https://github.com/ntu-csie-train/telegram-echo-bot-starter
  * [set-webhook](https://core.telegram.org/bots/api#setwebhook)
  * [incoming-message](https://core.telegram.org/bots/api#getting-updates)
  * [outgoing-message](https://core.telegram.org/bots/api#sendmessage)

## 作業
  * [homework](/homework.md)

## 補充資料
 ### URL 與 URI 
  * [URL Strings and URL Objects](https://nodejs.org/api/url.html)
  * [Uniform Resource Identifier](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier)
 ### Facebook Messenger Platform Getting Started
  * [setup](https://developers.facebook.com/docs/messenger-platform/guides/setup)
 ### [ngrok](https://ngrok.com/)
  * 這個套件可以讓 localhost 的連結被外面連進來，而且還支援 https，適合開發 chatbot 的時候 debug

 ### [postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=zh-TW)
  * Chrome 的插件，可以用來傳送 HTTP request
