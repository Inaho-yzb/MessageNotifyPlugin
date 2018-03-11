# MessageNotifyPlugin 消息通知显示插件
A jQuery message notify plugin
基于jQuery的一个消息通知显示插件

使用方法：

1.设置容器元素，引入js， css
```html
<script src="js/jquery-3.3.1.min.js"></script>
<script src="js/message.js"></script>
<link rel="stylesheet" href="css/message.css">
```
```html
<body>
    <div id="message"></div>
</body>
```

2.初始化
```javascript
MessagePlugin.init({
                elem: "#message",
                msgData: [{text: "message1", id: 1, readStatus: 1},
                    {text: "message2", id: 2, readStatus: 0},
                    {text: "message3", id: 3, readStatus: 0},
                    {text: "message4", id: 4, readStatus: 0},
                    {text: "message5", id: 5, readStatus: 0},
                    {text: "message6", id: 6, readStatus: 0}],
                    msgUnReadData: 99,
                    noticeUnReadData: 99,
                    msgClick: function(obj) {
                        alert("消息点击事件");
                    },
                    noticeClick: function(obj) {
                        alert("提醒点击事件");
                    },
                    allRead: function(obj) {
                        alert("全部已读");
                    },
                    getNodeHtml: function(obj, node) {
                        if (obj.readStatus == 1) {
                            node.isRead = true;
                        } else {
                            node.isRead = false;
                        }
                        var html = "<p>"+ obj.text +"</p>";

                        node.html = html;

                        return node;
                    }
            });
```

效果： 

<img src="https://s1.ax2x.com/2018/03/11/EOneE.png" width="250">
