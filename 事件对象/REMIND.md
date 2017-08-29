* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 十一、事件对象

#### 1、event.currentTarget 在事件冒泡阶段中的[*事件绑定的那个DOM元素*]
    这是注册事件时的对象，不是它的子元素
* 参数：
    * 1）无

#### 2、event.data 当前执行的处理器被绑定的时候，包含可选的数据传递给jQuery.fn.bind。
* 参数：
    * 1）无

#### 3、event.delegateTarget 当currently-called的jQuery事件处理程序附加元素，附加在[*正在处理的元素的祖先*]上。[1.7+]
    此属性是最经常有用是通过过.delegate() 或.on()附加委派的事件，事件处理程序附加在正在处理的元素的祖先上。
    它可用于，例如，指明委派识别和删除事件处理程序。 

    对于非授权的事件处理程序，直接连接到一个元素，event.delegateTarget 总是等价于event.currentTarget.
* 参数：
    * 1）无

#### 4、event.isDefaultPrevented() 根据事件对象中是否调用过 event.preventDefault() 方法来返回一个布尔值。
* 参数：
    * 1）无

#### 5、event.isImmediatePropagationStopped() 根据事件对象中是否调用过 
    检测event.stopImmediatePropagation() 方法来返回一个布尔值。
* 参数：
    * 1）无

#### 6、event.isPropagationStopped() 根据事件对象中是否调用过 
    检测event.stopPropagation() 方法来返回一个布尔值。
* 参数：
    * 1）无

#### 7、event.namespace 当事件被触发时此属性包含指定的命名空间。
* 参数：
    * 1）无

#### 8、event.pageX 鼠标相对于文档的左边缘的位置。
* 参数：
    * 1）无

#### 9、event.pageY 鼠标相对于文档的上边缘的位置。
* 参数：
    * 1）无

#### 10、event.preventDefault() 阻止默认事件行为的触发。
    例如，在执行这个方法后，如果点击一个锚点，就不会让浏览器跳转到新的 URL 去了。
    我们可以用 event.isDefaultPrevented() 来确定这个方法是否(在那个事件对象上)调用过了。
* 参数：
    * 1）无

#### 11、event.relatedTarget 在事件中涉及的其它任何DOM元素。
    对于 mouseout 事件，它指向被进入的元素；对于 mousein 事件，它指向被离开的元素。
* 参数：
    * 1）无

#### 12、event.result 这个属性包含了当前事件事件最后触发的那个处理函数的返回值，除非值是 undefined 。
* 参数：
    * 1）无

#### 13、event.stopImmediatePropagation() 阻止剩余的事件处理函数执行并且防止事件冒泡到DOM树上。
    除了阻止元素上其它的事件处理函数的执行，这个方法还会通过在内部调用 event.stopPropagation() 来停止事件冒泡。
    
    重点：如果仅仅想要停止事件冒泡到前辈元素上，而让这个元素上的其它事件处理函数继续执行，
        我们可以使用event.stopPropagation() 来代替。
    
    使用 event.isImmediatePropagationStopped() 来确定这个方法是否(在那个事件对象上)调用过了。

    注意:
    自从.live()方法处理事件一旦传播到文档的顶部，live事件是不可能停止传播的。
    同样地，.delegate() 事件将始终传播给其中包含的被委托元素；
    元素上的事件将在被委托事件被调用的时候执行。
* 参数：
    * 1）无

#### 14、event.stopPropagation() 防止事件冒泡到DOM树上，也就是不触发的任何前辈元素上的事件处理函数。
    我们可以用 event.isPropagationStopped() 来确定这个方法是否(在那个事件对象上)调用过了。
    这个方法对 trigger() 来自定义的事件同样有效。

    注意，这不会阻止同一个元素上的其它事件处理函数的运行。
    
    说明：
    自从.live()方法处理事件一旦传播到文档的顶部，live事件是不可能停止传播的。
    同样地，.delegate() 事件将始终传播给其中包含的被委托元素；
    元素上的事件将在被委托事件被调用的时候执行。
* 参数：
    * 1）无

#### 15、event.target 最初触发事件的DOM元素，在事件冒泡阶段中的当前DOM元素。
    这是注册事件时的对象，或者它的子元素。
    通常用于比较 event.target 和 this 来确定事件是不是由于冒泡而触发的。
    经常用于事件冒泡时处理事件委托。
* 参数：
    * 1）无

#### 16、event.timeStamp 这个属性返回事件触发时距离1970年1月1日的毫秒数。
    这可以很方便的检测某个jQuery函数的性能。
* 参数：
    * 1）无

#### 17、event.type 当前触发的事件类型。
* 参数：
    * 1）无

#### 18、event.which 针对键盘和鼠标事件，这个属性能确定你到底按的是哪个键或按钮。
    event.which 将 event.keyCode 和 event.charCode 标准化了。
    推荐用 event.which 来监视键盘输入。
* 参数：
    * 1）无
    


