* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 十一、事件对象

#### 1、event.currentTarget 在事件冒泡阶段中的当前DOM元素
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




