* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 四、属性部分

#### 1、attr(name|properties|key,value|fn) 设置或返回被选元素的属性值
* 参数：
    * 1）name 属性名
    * 2）properties 属性的"名/值对"对象
    * 3）key,value 属性名称，属性值
    * 4）key,function(index, attr) 
        属性名称
        返回属性值的函数,第一个参数为当前元素的索引值，第二个参数为原先的属性值

#### 2、removeAttr(name) 从每一个匹配的元素中删除一个属性
    1.6以下版本在IE6使用JQuery的removeAttr方法删除disabled是无效的。
    解决的方法就是使用$("XX").prop("disabled",false);
    1.7版本在IE6下已支持删除disabled
* 参数：
    * 1）name 属性名

#### 3、prop(name|properties|key,value|fn) 获取在匹配的元素集中的第一个元素的属性值 [1.6+]
    随着一些内置属性的DOM元素或window对象，如果试图将删除该属性，浏览器可能会产生错误
    jQuery第一次分配undefined值的属性，而忽略了浏览器生成的任何错误
* 参数：
    * 1）name 属性名
    * 2）properties 属性的"名/值"对象
    * 3）key,value 属性名，属性值
    * 4）key,function(index, attr)
         属性名
         返回属性值的函数,第一个参数为当前元素的索引值，第二个参数为原先的属性值

#### 4、removeProp(name) 用来删除由.prop()方法设置的属性集 [1.6+]
    随着一些内置属性的DOM元素或window对象，如果试图将删除该属性，浏览器可能会产生错误
    jQuery第一次分配undefined值的属性，而忽略了浏览器生成的任何错误
    [*不能删除固有属性(含新增固有属性都不能删除)，只能删除 prop() 增加的非固有属性*]
* 参数：
    * 1）propertyName 属性名

#### 5、addClass(class|fn) 为每个匹配的元素添加指定的类名
* 参数：
    * 1）class 
        一个或多个要添加到元素中的CSS类名，请用空格分开
    * 2)function(index, class)
        此函数必须返回一个或多个空格分隔的class名。
        接受两个参数，index参数为对象在这个集合中的索引值
        class参数为这个对象原先的class属性值。

#### 6、removeClass([class|fn]) 从所有匹配的元素中删除全部或者指定的类
* 参数： 
    * 1）class 
        一个或多个要删除的CSS类名，请用空格分开
    * 2）function(index, class)
        此函数必须返回一个或多个空格分隔的class名。
        接受两个参数，index参数为对象在这个集合中的索引值
        class参数为这个对象原先的class属性值。

#### 7、toggleClass(class|fn[,sw]) 如果存在（不存在）就删除（添加）一个类
* 参数：
    * 1）class
    * 2) class,switch
        要切换的CSS类名.
        用于决定元素是否包含class的布尔值。
    * 3）function(index, class, switch)[,switch]
        用来返回在匹配的元素集合中的每个元素上用来切换的样式类名的一个函数。接收元素的索引位置和元素旧的样式类作为参数
        一个用来判断样式类添加还是移除的 boolean 值

#### 8、html([val|fn]) 取得第一个匹配元素的html内容。这个函数不能用于XML文档。但可以用于XHTML文档
    返回或设定HTML内容的值(无参数或有参数)
* 参数：
    * 1）val 用于设定HTML内容的值
    * 2）function(index, html)
        此函数返回一个HTML字符串。接受两个参数，index为元素在集合中的索引位置，html为原先的HTML值。

#### 9、text([val|fn]) 取得所有匹配元素的内容
    结果是由所有匹配元素包含的文本内容组合起来的文本。这个方法对HTML和XML文档都有效
* 参数：
    * 1）val 用于设置元素内容的文本
    * 2）function(index, text) 
        此函数返回一个字符串。接受两个参数，index为元素在集合中的索引位置，text为原先的text值

#### 10、val([val|fn|arr]) 获得匹配元素的当前值(第一个匹配元素)
    在 jQuery 1.2 中,可以返回任意元素的值了。包括select。如果多选，将返回一个数组，其包含所选的值
* 参数：
    * 1）val 要设置的值
    * 2）function(index, value)
        此函数返回一个要设置的值。接受两个参数，index为元素在集合中的索引位置，text为原先的text值。
    * 3）array
        用于 check/select 的值




