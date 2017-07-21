* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 五、CSS部分

#### 1、css(name|pro|[,val|fn]) 设置或访问匹配元素的样式属性
    jQuery 1.8中，当你使用CSS属性在css()或animate()中，我们将根据浏览器自动加上前缀(在适当的时候)
    比如("user-select", "none"); 在Chrome/Safari浏览器中我们将设置为"-webkit-user-select"
    Firefox会使用"-moz-user-select", IE10将使用"-ms-user-select".
* 参数：
    * 1）name 要访问的属性名称
    * 2）[name] 一个或多个CSS属性组成的一个数组
    * 3）properties 要设置为样式属性的名/值对
    * 4）name, value 属性名,属性值
    * 5）name,function(index, value)
        属性名
        此函数返回要设置的属性值。接受两个参数，index为元素在对象集合中的索引位置，value是原先的属性值。

#### 2、jQuery.cssHooks 直接向 jQuery 中添加钩子，用于覆盖设置或获取特定 CSS 属性时的方法
    目的是为了标准化 CSS 属性名或创建自定义属性
    $.cssHooks 对象提供了一种通过定义函数来获取或设置特定 CSS 值的方法。
    可以用它来创建新的 cssHooks 用于标准化 CSS3 功能，例如，盒子阴影（box shadows）及渐变（gradients）
    例如，某些基于 Webkit 的浏览器会使用 -webkit-border-radius 来设置对象的 border-radius，
    然而,早先版本的 Firefox 则使用 -moz-border-radius。cssHook 就可以将这些不同的写法进行标准化，
    从而让 .css() 可以使用统一的标准化属性名(border-radius 或对应的 DOM 属性写法 borderRadius)
    该方法除了提供了对特定样式的处理可以采用更加细致的控制外，$.cssHooks 同时还扩展了 .animate() 方法上的属性集
* 参数：
    * 1）无

#### 3、offset([coordinates]) 获取匹配元素在当前文档视口的相对偏移
    返回的对象包含两个整型属性：top 和 left，以像素计。此方法只对可见元素有效
* 参数：
    * 1）coordinates{top,left}
        必需。规定以像素计的 top 和 left 坐标
        值对，比如 {top:100,left:0}
        带有 top 和 left 属性的对象
    * 2）function(index,coords)
        规定返回被选元素新偏移坐标的函数
        index - 可选。接受选择器的 index 位置
        oldvalue - 可选。接受选择器的当前坐标

#### 4、position() 获取匹配元素相对父元素的偏移
    返回的对象包含两个整型属性：top 和 left
    为精确计算结果，请在补白、边框和填充属性上使用像素单位。此方法只对可见元素有效
* 参数： 
    * 1）无

#### 5、scrollTop([val]) 获取匹配元素相对滚动条顶部的偏移 
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）val 设定垂直滚动条值

#### 6、scrollLeft([val]) 获取匹配元素相对滚动条左侧的偏移
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）val 设定水平滚动条值
    
#### 7、height([val|fn]) 取得匹配元素当前计算的高度值（px）
    在 jQuery 1.2 以后可以用来获取 window 和 document 的高
* 参数：
    * 1）val 
        设定CSS中 'height' 的值，可以是字符串或者数字，还可以是一个函数，返回要设置的数值
        函数接受两个参数，第一个参数是元素在原先集合中的索引位置，第二个参数为原先的高度。
    * 2）function(index, height)
        返回用于设置高度的一个函数。接收元素的索引位置和元素旧的高度值作为参数
    
#### 8、width([val|fn]) 取得第一个匹配元素当前计算的宽度值（px）
    在 jQuery 1.2 以后可以用来获取 window 和 document 的宽
* 参数：
    * 1）val
        设定CSS中 'width' 的值，可以是字符串或者数字，还可以是一个函数，返回要设置的数值
        函数接受两个参数，第一个参数是元素在原先集合中的索引位置，第二个参数为原先的宽度。
    * 2）function(index, width)
        返回用于设置宽度的一个函数。接收元素的索引位置和元素旧的宽度值作为参数

#### 9、innerHeight() 获取第一个匹配元素内部区域高度（包括补白、不包括边框）
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）无

#### 10、innerWidth() 获取第一个匹配元素内部区域宽度（包括补白、不包括边框）
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）无

#### 11、outerHeight([options]) 获取第一个匹配元素外部高度（默认包括补白和边框）
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）options 设置为 true 时，计算边距在内，默认值:'false'

#### 12、outerWidth([options]) 获取第一个匹配元素外部宽度（默认包括补白和边框）
    此方法对可见和隐藏元素均有效
* 参数：
    * 1）options 设置为 true 时，计算边距在内，默认值:'false'


