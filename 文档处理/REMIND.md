* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 六、文档处理部分

#### 1、append(content|fn) 向每个匹配的元素内部追加内容
    这个操作与对指定的元素执行appendChild方法，将它们添加到文档中的情况类似
* 参数：
    * 1）content 要追加到目标中的内容
    * 2）function(index, html) 
        返回一个HTML字符串，用于追加到每一个匹配元素的里边
        接受两个参数，index参数为对象在这个集合中的索引值，html参数为这个对象原先的html值
    
#### 2、appendTo(content) 把所有匹配的元素追加到另一个指定的元素元素集合中
    实际上，使用这个方法是颠倒了常规的$(A).append(B)的操作，即不是把B追加到A中，而是把A追加到B中
    在jQuery 1.3.2中，appendTo, prependTo, insertBefore, insertAfter, 
    和 replaceAll这个几个方法成为一个破坏性操作，返回值是所有被追加的内容，
    而不仅仅是先前所选中的元素。所以，要选择先前选中的元素，需要使用end()方法
* 参数：
    * 1）content 用于被追加的内容

#### 3、prepend(content|fn) 向每个匹配的元素内部前置内容
    这是向所有匹配元素内部的开始处插入内容的最佳方式
* 参数：
    * 1）content 要插入到目标元素内部前端的内容
    * 2）function(index, html)
        返回一个HTML字符串，用于追加到每一个匹配元素的里边
        接受两个参数，index参数为对象在这个集合中的索引值，html参数为这个对象原先的html值
    
#### 4、prependTo(content) 把所有匹配的元素前置到另一个、指定的元素元素集合中
    实际上，使用这个方法是颠倒了常规的$(A).prepend(B)的操作，即不是把B前置到A中，而是把A前置到B中
    在jQuery 1.3.2中，appendTo, prependTo, insertBefore, insertAfter, 
    和 replaceAll这个几个方法成为一个破坏性操作，要选择先前选中的元素，需要使用end()方法
* 参数：
    * 1）content 用于匹配元素的jQuery表达式

#### 5、after(content|fn) 在每个匹配的元素之后插入内容
* 参数：
    * 1）content 插入到每个目标后的内容
    * 2）function 函数必须返回一个html字符串

#### 6、before(content|fn) 在每个匹配的元素之前插入内容
* 参数：
    * 1）content 插入到每个目标后的内容
    * 2）function 插入到每个目标后的内容

#### 7、insertAfter(content) 把所有匹配的元素插入到另一个、指定的元素元素集合的后面
    实际上，使用这个方法是颠倒了常规的$(A).after(B)的操作，即不是把B插入到A后面，而是把A插入到B后面
    在jQuery 1.3.2中，appendTo, prependTo, insertBefore, insertAfter, 
    和 replaceAll这个几个方法成为一个破坏性操作，要选择先前选中的元素，需要使用end()方法
* 参数：
    * 1）content 用于匹配元素的jQuery表达式

#### 8、insertBefore(content) 把所有匹配的元素插入到另一个、指定的元素元素集合的前面
    实际上，使用这个方法是颠倒了常规的$(A).before(B)的操作，即不是把B插入到A前面，而是把A插入到B前面
    在jQuery 1.3.2中，appendTo, prependTo, insertBefore, insertAfter, 
    和 replaceAll这个几个方法成为一个破坏性操作，要选择先前选中的元素，需要使用end()方法
* 参数：
    * 1）content 用于匹配元素的jQuery表达式

#### 9、wrap(html|element|fn) 把所有匹配的元素用其他元素的结构化标记包裹起来
    这种包装对于在文档中插入额外的结构化标记最有用，而且它不会破坏原始文档的语义品质。
    这个函数的原理是检查提供的第一个元素（它是由所提供的HTML标记代码动态生成的），
    并在它的代码结构中找到最上层的祖先元素－－这个祖先元素就是包裹元素。
    当HTML标记代码中的元素包含文本时无法使用这个函数。因此，如果要添加文本应该在包裹完成之后再行添加。
* 参数：
    * 1）html HTML标记代码字符串，用于动态生成元素并包裹目标元素
    * 2）element 用于包装目标元素的DOM元素
    * 3）fn 生成包裹结构的一个函数
    
#### 10、unwrap() 这个方法将移出元素的父元素。这能快速取消 .wrap()方法的效果
    匹配的元素（以及他们的同辈元素）会在DOM结构上替换他们的父元素
* 参数：
    * 1）无

#### 11、wrapAll(html|ele) 将所有匹配的元素用单个元素包裹起来
    这于 '.wrap()'<a href="http://docs.jquery.com/Manipulation/wrap" title="Manipulation/wrap"></a> 是不同的，'.wrap()'为每一个匹配的元素都包裹一次
    这种包装对于在文档中插入额外的结构化标记最有用，而且它不会破坏原始文档的语义品质。
    这个函数的原理是检查提供的第一个元素并在它的代码结构中找到最上层的祖先元素－－这个祖先元素就是包装元素。
* 参数： 
    * 1）html TML标记代码字符串，用于动态生成元素并包装目标元素
    * 2）elem 用于包装目标元素的DOM元素

#### 12、wrapInner(htm|element|fnl) 将每一个匹配的元素的子内容(包括文本节点)用一个HTML结构包裹起来
    这个函数的原理是检查提供的第一个元素（它是由所提供的HTML标记代码动态生成的）
    并在它的代码结构中找到最上层的祖先元素－－这个祖先元素就是包装元素。
* 参数：
    * 1）html HTML标记代码字符串，用于动态生成元素并包装目标元素
    * 2）element 用于包装目标元素的DOM元素
    * 3）fn 生成包裹结构的一个函数

#### 13、replaceWith(content|fn) 将所有匹配的元素替换成指定的HTML或DOM元素
* 参数： 
    * 1）content
        用于将匹配元素替换掉的内容。如果这里传递一个函数进来的话，函数返回值必须是HTML字符串
    * 2）fn 返回THML字符串，用来替换的内容
        有相同element时，你发现他是移动到目标位置来替换，而不是复制一份来替换

#### 14、replaceAll(selector) 用匹配的元素替换掉所有 selector匹配到的元素
    在jQuery 1.3.2中，appendTo, prependTo, insertBefore, insertAfter
    和 replaceAll这个几个方法成为一个破坏性操作，要选择先前选中的元素，需要使用end()方法
* 参数：
    * 1） selector 用于查找所要被替换的元素

#### 15、empty() 删除匹配的元素集合中所有的子节点
* 参数：
    * 1）无

#### 16、remove([expr]) 从DOM中删除所有匹配的元素
    这个方法不会把匹配的元素从jQuery对象中删除，因而可以在将来再使用这些匹配的元素。
    但除了这个元素本身得以保留之外，其他的比如绑定的事件，附加的数据等都会被移除。
* 参数：
    * 1）expr
        用于筛选元素的jQuery表达式

#### 17、detach([expr]) 从DOM中删除所有匹配的元素
    这个方法不会把匹配的元素从jQuery对象中删除，因而可以在将来再使用这些匹配的元素。
    与remove()不同的是，所有绑定的事件、附加的数据等都会保留下来
* 参数：
    * 1）expr
        用于筛选元素的jQuery表达式

#### 18、clone([Even[,deepEven]]) 克隆匹配的DOM元素并且选中这些克隆的副本
    在想把DOM文档中元素的副本添加到其他位置时这个函数非常有用
* 参数：
    * 1）Events
        一个布尔值（true 或者 false）指示事件处理函数是否会被复制。V1.5以上版本默认值是：false
    * 2）Events[,deepEvents]
        一个布尔值（true 或者 false）指示事件处理函数是否会被复制
        一个布尔值，指示是否对事件处理程序和克隆的元素的所有子元素的数据应该被复制
