* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 八、事件部分

#### 1、ready(fn) 当DOM载入就绪可以查询及操纵时绑定一个要执行的函数。
    这是事件模块中最重要的一个函数，因为它可以极大地提高web应用程序的响应速度。
    简单地说，这个方法纯粹是对向window.load事件注册事件的替代方法。
    通过使用这个方法，可以在DOM载入就绪能够读取并操纵时立即调用你所绑定的函数，
    而99.99%的JavaScript函数都需要在那一刻执行。

    有一个参数－－对jQuery函数的引用－－会传递到这个ready事件处理函数中。
    可以给这个参数任意起一个名字，并因此可以不再担心命名冲突而放心地使用$别名。

    请确保在 <body> 元素的onload事件中没有注册函数，
    否则不会触发+$(document).ready()事件。
    可以在同一个页面中无限次地使用$(document).ready()事件。
    其中注册的函数会按照（代码中的）先后顺序依次执行。

    使用 $(document).ready() 的简写，同时内部的 jQuery 代码依然使用 $ 作为别名，而不管全局的 $ 为何。
* 参数：
    * 1）fn 要在DOM就绪时执行的函数

#### 2、on(event,[selector],[data],fn) 在选择元素上绑定一个或多个事件的事件处理函数。[1.7+]
    on()方法绑定事件处理程序到当前选定的jQuery对象中的元素。
    在jQuery 1.7中，.on()方法 提供绑定事件处理程序所需的所有功能。
    帮助从旧的jQuery事件方法转换，see .bind(), .delegate(), 和 .live()；
    要删除的.on()绑定的事件，请参阅.off()。
    要附加一个事件，只运行一次，然后删除自己， 请参阅.one()
* 参数：
    * 1）event,[selector],[data],fn
        events:一个或多个用空格分隔的事件类型和可选的命名空间，如"click"或"keydown.myPlugin" 。
        selector:一个选择器字符串用于过滤器的触发事件的选择器元素的后代。
            如果选择的< null或省略，当它到达选定的元素，事件总是触发。
        data:当一个事件被触发时要传递event.data给事件处理函数。
        fn:该事件被触发时执行的函数。 false 值也可以做一个函数的简写，返回false。
    * 2）events-map,[selector],[data]
        events-map:一个用字符串表示的，一个或多个空格分隔的事件类型和可选的命名空间，值表示事件绑定的处理函数。
        selector:一个选择器字符串过滤选定的元素，该选择器的后裔元素将调用处理程序。
            如果选择是空或被忽略，当它到达选定的元素，事件总是触发。
        data:当一个事件被触发时要传递event.data给事件处理函数。


