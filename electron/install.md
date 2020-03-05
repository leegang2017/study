## 如何解决Electron安装包下载慢的问题
可以先在这里下载安装包：
https://npm.taobao.org/mirrors/electron/

然后，将安装包（.zip文件）拷贝到以下路径（Mac）：

~/.electron/

然后继续安装electron就可以了：

npm i electron

## 解决npm一直停在"node ./download-chromedriver.js"的问题
npm install chromedriver --chromedriver_cdnurl=http://cdn.npm.taobao.org/dist/chromedriver
