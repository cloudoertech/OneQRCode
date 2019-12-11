# OneQRCode
微信、支付宝、QQ 三合一收款二维码（单页版）

## 注意事项

 - 使用前将 `index.html` 中的收款链接改成你自己的；
 - 请用专门的 Html 编辑器(如 notepad++)进行编辑，切勿直接用记事本编辑，否则可能出现中文乱码！
 - 请将 `index.html` 上传至你的网站空间使用。直接在本地打开将无法运行；

## 原理
在 微信、支付宝、QQ 中扫描到一个网址二维码后，一般会通过内置的浏览器打开这个网址。通过判断内置浏览器的 UA，即可得出当前扫码的具体支付平台。

````
if(navigator.userAgent.match(/Alipay/i)) {
    // 支付宝
} else if(navigator.userAgent.match(/MicroMessenger\//i)) {
    // 微信
} else if(navigator.userAgent.match(/QQ\//i)) {
    // QQ
} else {
    // 其它
}
````

其中，支付宝可以通过直接跳转收款链接唤起付款功能，而 QQ、微信 则需展示出对应的收款码，由用户自行长按识别真正的收款二维码实现唤起付款。