Puppeteer
### 1. 安装 puppeteer

```sh
yarn add puppeteer 或者 npm i puppeteer
```
下载慢
npm config set PUPPETEER_DOWNLOAD_HOST=https://npm.taobao.org/mirrors
npm install --save puppeteer

可能会出现以下报错:

```sh
ERROR: Failed to download Chromium r515411! Set "PUPPETEER_SKIP_CHROMIUM_DOWNLOA
D" env variable to skip download.

```

是因为在执行安装的过程中需要执行install.js，这里会下载Chromium,官网建议是进行跳过，我们可以执行 —ignore-scripts 忽略这个js执行。也可以通过设置环境变量set PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=1阻止下载 Chromium （因为封网，直接下载会失败）

```sh
npm i --save puppeteer --ignore-scripts
```
也可以手动安装chrome

```sh
sudo apt install google-chrome
```
### 2.  截图功能
```sh
const puppeteer = require('puppeteer');

(async () => {
    const browser = await puppeteer.launch({ executablePath: 'google-chrome' });
    const page = await browser.newPage();
    await page.goto('https://y.qq.com');
    await page.screenshot({path: 'yqq.png'});
    browser.close();
})();

```