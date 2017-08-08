* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 九、效果部分

#### 1、show([speed,[easing],[fn]]) 显示隐藏的匹配元素。
    这个就是 'show( speed, [callback] )' 无动画的版本。如果选择的元素是可见的，这个方法将不会改变任何东西。
    无论这个元素是通过hide()方法隐藏的还是在CSS里设置了display:none;，这个方法都将有效。
* 参数：
    * 1）speed [,fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 2、hide([speed,[easing],[fn]]) 隐藏显示的元素
    这个就是 'hide( speed, [callback] )' 的无动画版。如果选择的元素是隐藏的，这个方法将不会改变任何东西。
* 参数：
    * 1）speed[,fn] 
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 3、toggle([speed],[easing],[fn]) 用于绑定两个或多个事件处理器函数，以响应被选元素的轮流的 click 事件。
    如果元素是可见的，切换为隐藏的；如果元素是隐藏的，切换为可见的。
    1.9版本 .toggle(function, function, … ) 方法删除,jQuery Migrate（迁移）插件可以恢复此功能。
* 参数：
    * 1）[speed] [,fn]
        speed: 隐藏/显示 效果的速度。默认是 "0"毫秒。可能的值：slow，normal，fast。"
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed], [easing ], [fn ]
        speed: 隐藏/显示 效果的速度。默认是 "0"毫秒。可能的值：slow，normal，fast。"
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 3）switch
        用于确定显示/隐藏的开关。如：true - 显示元素，false - 隐藏元素

#### 4、slideDown([speed],[easing],[fn]) 通过高度变化（向下增大）来动态地显示所有匹配的元素
    在显示完成后可选地触发一个回调函数。
    这个动画效果只调整元素的高度，可以使匹配的元素以“滑动”的方式显示出来。
    在jQuery 1.3中，上下的padding和margin也会有动画，效果更流畅。
* 参数：
    * 1）speed[,fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn在动画完成时执行的函数，每个元素执行一次。

#### 5、slideUp([speed],[easing],[fn]) 通过高度变化（向上减小）来动态地隐藏所有匹配的元素
    在隐藏完成后可选地触发一个回调函数。
    这个动画效果只调整元素的高度，可以使匹配的元素以“滑动”的方式隐藏起来。
    在jQuery 1.3中，上下的padding和margin也会有动画，效果更流畅。
* 参数：
    * 1）speed[,fn] 
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 6、slideToggle([speed],[easing],[fn]) 通过高度变化来切换所有匹配元素的可见性，并在切换完成后可选地触发一个回调函数。
    这个动画效果只调整元素的高度，可以使匹配的元素以“滑动”的方式隐藏或显示。
    在jQuery 1.3中，上下的padding和margin也会有动画，效果更流畅。
* 参数：
    * 1）speed[,fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        n:在动画完成时执行的函数，每个元素执行一次。

#### 7、fadeIn([speed],[easing],[fn]) 通过不透明度的变化来实现所有匹配元素的淡入效果
    并在动画完成后可选地触发一个回调函数。
    这个动画只调整元素的不透明度，也就是说所有匹配的元素的高度和宽度不会发生变化。
* 参数：
    * 1）speed[,fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 8、 fadeOut([speed],[easing],[fn]) 通过不透明度的变化来实现所有匹配元素的淡出效果
    并在动画完成后可选地触发一个回调函数。
    这个动画只调整元素的不透明度，也就是说所有匹配的元素的高度和宽度不会发生变化。
* 参数：
    * 1）speed[,fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 9、fadeTo([[speed],opacity,[easing],[fn]]) 把所有匹配元素的不透明度以渐进方式调整到指定的不透明度
    并在动画完成后可选地触发一个回调函数。
    这个动画只调整元素的不透明度，也就是说所有匹配的元素的高度和宽度不会发生变化。
* 参数：
    * 1）speed,opacity,[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        opacity:一个0至1之间表示透明度的数字。
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],opacity,[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        opacity:一个0至1之间表示透明度的数字。
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 10、fadeToggle([speed,[easing],[fn]]) 通过不透明度的变化来开关所有匹配元素的淡入和淡出效果
    并在动画完成后可选地触发一个回调函数。
    这个动画只调整元素的不透明度，也就是说所有匹配的元素的高度和宽度不会发生变化。
* 参数：
    * 1）speed[,fn] 
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次。

#### 11、animate(params,[speed],[easing],[fn]) 用于创建自定义动画的函数。[1.8+]
    这个函数的关键在于指定动画形式及结果样式属性对象。
    这个对象中每个属性都表示一个可以变化的样式属性（如“height”、“top”或“opacity”）。
    注意：所有指定的属性必须用骆驼形式，比如用marginLeft代替margin-left.

    而每个属性的值表示这个样式属性到多少时动画结束。
    如果是一个数值，样式属性就会从当前的值渐变到指定的值。
    如果使用的是“hide”、“show”或“toggle”这样的字符串值，则会为该属性调用默认的动画形式。

    在 jQuery 1.2 中，你可以使用 em 和 % 单位。
    另外，在 jQuery 1.2 中，你可以通过在属性值前面指定 "<em>+=</em>" 或 "<em>-=</em>" 来让元素做相对运动。
    jQuery 1.3中，如果duration设为0则直接完成动画。而在以前版本中则会执行默认动画。

    jQuery 1.8中，当你使用CSS属性在css()或animate()中，
    我们将根据浏览器自动加上前缀(在适当的时候)，比如("user-select", "none");
    在Chrome/Safari浏览器中我们将设置为"-webkit-user-select", 
    Firefox会使用"-moz-user-select", IE10将使用"-ms-user-select".
* 参数：
    * 1）params,[speed],[easing],[fn]
        params:一组包含作为动画属性和终值的样式属性和及其值的集合
        speed:三种预定速度之一的字符串("slow","normal", or "fast")或表示动画时长的毫秒数值(如：1000)
        easing:要使用的擦除效果的名称(需要插件支持).默认jQuery提供"linear" 和 "swing".
        fn:在动画完成时执行的函数，每个元素执行一次
    * 2）params,options
        params::一组包含作为动画属性和终值的样式属性和及其值的集合
        options:动画的额外选项。
            如：speed - 设置动画的速度,easing - 规定要使用的 easing 函数,
            callback - 规定动画完成之后要执行的函数,step - 规定动画的每一步完成之后要执行的函数,
            queue - 布尔值。指示是否在效果队列中放置动画。
            如果为 false，则动画将立即开始,specialEasing - 来自 styles 参数的一个或多个 CSS 属性的映射，
            以及它们的对应 easing 函数

#### 12、stop([clearQueue],[jumpToEnd]) 停止所有在指定元素上正在运行的动画。[1.7+]
    如果队列中有等待执行的动画(并且clearQueue没有设为true)，他们将被马上执行
* 参数：
    * 1）[clearQueue],[gotoEnd]
        clearQueue:如果设置成true，则清空队列。可以立即结束动画。
        gotoEnd:让当前正在执行的动画立即完成，并且重设show和hide的原始样式，调用回调函数等。
    * 2）[queue],[clearQueue],[jumpToEnd]
        queue:用来停止动画的队列名称
        clearQueue:如果设置成true，则清空队列。可以立即结束动画。
        jumpToEnd:如果设置成true，则完成队列。可以立即完成动画。

#### 13、delay(duration,[queueName]) 设置一个延时来推迟执行队列中之后的项目。
    jQuery 1.4新增。用于将队列中的函数延时执行。
    他既可以推迟动画队列的执行，也可以用于自定义队列。
* 参数：
    * 1）duration,[queueName]
        duration:延时时间，单位：毫秒
        queueName:队列名词，默认是Fx，动画队列。

#### 14、finish([queue]) 停止当前正在运行的动画，删除所有排队的动画，并完成匹配元素所有的动画。[1.9+]
    当.finish()在一个元素上被调用，立即停止当前正在运行的动画和所有排队的动画（如果有的话），
    并且他们的CSS属性设置为它们的目标值（所有动画的目标值）。所有排队的动画将被删除。

    如果第一个参数提供，该字符串表示的队列中的动画将被停止。

    .finish()方法和.stop(true, true)很相似，.stop(true, true)将清除队列，并且目前的动画跳转到其最终值。
    但是，不同的是，.finish() 会导致所有排队的动画的CSS属性跳转到他们的最终值。
* 参数：
    * 1）queue
        停止动画队列中的名称。

#### 15、jQuery.fx.off 关闭页面上所有的动画。
    把这个属性设置为true可以立即关闭所有动画(所有效果会立即执行完毕)。有些情况下可能需要这样
    比如：
    1、你在配置比较低的电脑上使用jQuery。
    2、你的一些用户由于动画效果而遇到了 可访问性问题

    当把这个属性设成false之后，可以重新开启所有动画。
* 参数：
    * 1）无

#### 16、jQuery.fx.interval 设置动画的显示帧速。
* 参数：
    * 1）无
    



