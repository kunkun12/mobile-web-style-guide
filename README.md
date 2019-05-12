# 移动Web开发规范
整理网上的以及自己常用的移动开发规范。。

## 字体设置

    body {
        font-family: "Helvetica Neue",Helvetica,"Hiragino Sans GB","STHeitiSC-Light","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    }
     html ,body{
     overflow-x: hidden; //如果页面可以左右拖动 可以试试这个隐藏横向溢出内容，禁止左右拖动
     }
     
## 基础交互

    a, img {
        -webkit-touch-callout: none; /* 禁止长按链接与图片弹出菜单 */
    }
    html, body {
        -webkit-user-select: none;   /* 禁止选中文本（如无文本选中需求，此为必选项） */
        user-select: none;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    }
    a,input,button {
    outline:none // 按钮点击之后会有边框
    }
    *,*:before,*:after{
        -webkit-box-sizing:border-box;
        box-sizing:border-box;
    }
    
## viewport

    <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no, width=device-width">
    
       （Hybrid）   Android 4.4.x meta viewport 默认不起作用，需要创建webview的时候设置
    
            WebSettings settings = webView.getSettings();
            settings.setLoadWithOverviewMode(true);
            settings.setUseWideViewPort(true);

其他meta 

    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">       //编码
    <meta name="apple-mobile-web-app-capable" content="yes" />                // 离线应用的另一个技巧         
    <meta content="black" name="apple-mobile-web-app-status-bar-style" />     //指定的iphone中safari顶端的状态条的样式       
    <meta content="telephone=no" name="format-detection" />                   //告诉设备忽略将页面中的数字识别为电话号码     
    <meta name="Author" contect="Mr.He"/ >
  
## 特殊链接

    <a href="tel:12345654321">打电话给我</a>
    <a href="sms:12345654321">发短信</a>
    或用于单元格：
    <td onclick="location.href='tel:122'">
    <input type="text" x-webkit-speech /> <!--语音输入-->
    <input type="file" accept ="image/*; capture=camera" /> <!--文件上传, 从相机捕获媒体, 下同-->
    <input type="file" accept = "video/*; capture=camcorder" />
    <input type="file" accept = "audio/*; capture=microphone" />
    <a href="sms:18005555555,18005555556"></a> <!--发送短信给多个人 的链接-->
    <a href="sms:18005555555?body=helloWorld"></a> <!--发送短信附带内容 的链接-->
    <a href="tel:18005555555″>Call us at 1-800-555-5555</a> <!--拨打电话 的链接-->

## 手势事件 

// 手势事件
- touchstart            //当手指接触屏幕时触发
- touchmove           //当已经接触屏幕的手指开始移动后触发
- touchend             //当手指离开屏幕时触发
- touchcancel
 
IOS safari 浏览器下禁用页面拖动效果

        document.body.addEventListener('touchstart', function (ev) { 
                  ev.preventDefault();
            });
// 触摸事件
- gesturestart          //当两个手指接触屏幕时触发
- gesturechange      //当两个手指接触屏幕后开始移动时触发
- gestureend
 

- onorientationchange    // 屏幕旋转事件  
 
// 检测触摸屏幕的手指何时改变方向      
- orientationchange      
 
// touch事件支持的相关属性
- touches        
- targetTouches      
- changedTouches             
- clientX　clientY　　　// 相对视口的坐标（不包括滚动）  
- screenX screenY 　　　 // 相对屏幕     
- pageX pageY　 　　// 相对文档

## 调试工具

- [weinre](http://people.apache.org/~pmuellr/weinre/)
- [jsconsole](http://jsconsole.com/)  [本地部署](https://github.com/remy/jsconsole)
- [vorlon](http://vorlonjs.com/)
- 对于android4.0 的chrome 以及 4.4之后的webview可以采用浏览器的远程调试[官方教程](https://developer.chrome.com/devtools/docs/remote-debugging) 

[移动端webapp开发必备知识](https://www.qianduan.net/mobile-webapp-develop-essential-knowledge/)
