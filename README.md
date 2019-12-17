## 安卓通过调用JS去调用StompSocket

新建一个html文件test，把所有js文件引进来

```html
<!DOCTYPE html>

<html>
<head>
    <meta http-equiv="Access-Control-Allow-Origin" content="*" />
    <title></title>
</head>
<body>

<script src="js/message.js"></script>

<script src="js/stomp.min.js"></script>

<script src="js/sockjs.min.js"></script>

</body>
```

在Activity里面配置
```java
mWebView.getSettings().setJavaScriptEnabled(true);
        mWebView.addJavascriptInterface(new JsToJava(), "stub");  //JsToJava是内部类，代码在后面。stub是接口名字。
        mWebView.loadUrl("file:///android_asset/test.html"); //加载本地html文件
        
String url = "javascript:connect('http://newh5.ly9900.com/message/access','33333333333:12345655555','24','3')"; //调用js connect方法
mWebView.loadUrl(url);
        
```

![图片名称](/app/src/main/res/mipmap-hdpi/ic_launcher.png  "picture")






