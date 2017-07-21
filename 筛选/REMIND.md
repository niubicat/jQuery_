* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 七、筛选部分

#### 1、eq(index|-index) 获取当前链式操作中第N个jQuery对象，返回jQuery对象
    当参数大于等于0时为正向选取，比如0代表第一个，1代表第二个。当参数为负数时为反向选取，比如-1为倒数第一个
    类似的有get(index),不过get(index)返回的是DOM对象
* 参数：
    * 1）index
        一个整数，指示元素基于0的位置,这个元素的位置是从0算起
    * 2）-index
        一个整数，指示元素的位置，从集合中的最后一个元素开始倒数。(-1算起)

#### 2、first() 获取第一个元素
* 参数：
    * 1）无

#### 3、last() 获取最后一个元素
* 参数：
    * 1）无

#### 4、hasClass(class) 检查当前的元素是否含有某个特定的类，如果有，则返回true
    这其实就是 is("." + class)
* 参数：
    * 1）class
        用于匹配的类名

#### 5、filter(expr|obj|ele|fn) 筛选出与指定表达式匹配的元素集合
    这个方法用于缩小匹配的范围。用逗号分隔多个表达式
* 参数：
    * 1）expr
        字符串值，包含供匹配当前元素集合的选择器表达式
    * 2）jquery object
        现有的jQuery对象，以匹配当前的元素
    * 3）element
        一个用于匹配元素的DOM元素
    * 4）function(index)
        一个函数用来作为测试元素的集合。它接受一个参数index，这是元素在jQuery集合的索引。
        在函数， this指的是当前的DOM元素。

#### 6、is(expr|obj|ele|fn) 根据选择器、DOM元素或 jQuery 对象来检测匹配元素集合 [1.6+]
    如果其中至少有一个元素符合这个给定的表达式就返回true
    如果没有元素符合，或者表达式无效，都返回'false'
    注意：在jQuery 1.3中才对所有表达式提供了支持。
    在先前版本中，如果提供了复杂的表达式，比如层级选择器（比如 + , ~ 和 > ），始终会返回true
*  参数：
    * 1）expr
        字符串值，包含供匹配当前元素集合的选择器表达式
    * 2）jquery object
        现有的jQuery对象，以匹配当前的元素
    * 3）element
        一个用于匹配元素的DOM元素
    * 4）function(index)
        一个函数用来作为测试元素的集合。它接受一个参数index，这是元素在jQuery集合的索引。
        在函数， this指的是当前的DOM元素

#### 7、map(callback) 将一组元素转换成其他数组（不论是否是元素数组)，返回的是jquery对象
    需要get()转化为dom对象，才能append()／appendTo()。
    你可以用这个函数来建立一个列表，不论是值、属性还是CSS样式，或者其他特别形式。这都可以用'$.map()'来方便的建立
* 参数：
    * 1）callback
        给每个元素执行的函数

#### 8、has(expr|ele) 保留包含特定后代的元素，去掉那些不含有指定后代的元素
    .has()方法将会从给定的jQuery对象中重新创建一组匹配的对象。
    提供的选择器会一一测试原先那些对象的后代，含有匹配后代的对象将得以保留。
* 参数：
    * 1）expr
        一个选择器字符串
    * 2）element
        一个DOM元素

#### 9、not(expr|ele|fn) 从匹配元素的集合中删除与指定表达式匹配的元素
* 参数：
    * 1）expr
        一个选择器字符串
    * 2）element
        一个DOM元素
    * 3）function(index)
        一个用来检查集合中每个元素的函数。this是当前的元素

#### 10、slice(start, [end]) 选取一个匹配的子集
    与原来的slice方法类似
* 参数：
    * 1）start
        开始选取子集的位置。第一个元素是0.如果是负数，则可以从集合的尾部开始选起
    * 2）end
        结束选取自己的位置，如果不指定，则就是本身的结尾

#### 11、children([expr]) 取得一个包含匹配的元素集合中每一个元素的所有子元素的元素集合
    可以通过可选的表达式来过滤所匹配的子元素。
    注意：parents()将查找所有祖辈元素，而children()只考虑子元素而不考虑所有后代元素
* 参数：
    * 1）expr
        用以过滤子元素的表达式

#### 12、closest(expr|object|element) jQuery 1.3新增。从元素本身开始，逐级向上级元素匹配，并返回最先匹配的元素 [1.7-]
    closest会首先检查当前元素是否匹配，如果匹配则直接返回元素本身。
    如果不匹配则向上查找父元素，一层一层往上，直到找到匹配选择器的元素。
    如果什么都没找到则返回一个空的jQuery对象。
    
    * closest和parents的主要区别是：
    1，前者从当前元素开始匹配寻找，后者从父元素开始匹配寻找；
    2，前者逐级向上查找，直到发现匹配的元素后就停止了，后者一直向上查找直到根元素，
        然后把这些元素放进一个临时集合中，再用给定的选择器表达式去过滤；
    3，前者返回0或1个元素，后者可能包含0个，1个，或者多个元素。

    * closest对于处理事件委托非常有用。

    * .closest( selectors [, context ] )方法从 jQuery 1.7 开始，不再建议使用该方法，[1.7-]
        但是 jQuery 1.7 之前仍然可以使用。
        该方法将主要用于 jQuery 内部或插件作者使用。

* 参数：
    * 1、expr 
        用以过滤元素的表达式。jQuery 1.4开始，也可以传递一个字符串数组，用于查找多个元素。
    * 2、jQuery object 
        一个用于匹配元素的jQuery对象
    * 3、element
        一个用于匹配元素的DOM元素
        
#### 13、find(expr|obj|ele) 搜索所有与指定表达式匹配的元素。这个函数是找出正在处理的元素的[*后代元素*]的好方法 [1.6+]
    所有搜索都依靠jQuery表达式来完成。这个表达式可以使用CSS1-3的选择器语法来写
* 参数：
    * 1、expr
        用于查找的表达式
    * 2、jquery object
        一个用于匹配元素的jQuery对象
    * 3、element
        一个DOM元素

#### 14、next([expr]) 取得一个包含匹配的元素集合中每一个元素紧邻的后面同辈元素的元素集合
    紧邻的同辈元素
* 参数：
    * 1、expr
        用于筛选的表达式

#### 15、nextAll([expr]) 查找当前元素之后所有的同辈元素
    可以用表达式过滤
* 参数：
    * 1、expr
        用来过滤的表达式
    
#### 16、nextUntil([exp|ele][,fil]) 查找当前元素之后所有的同辈元素，直到遇到匹配的那个元素为止 [1.6+]
    如果提供的jQuery代表了一组DOM元素，.nextUntil()方法也能让我们找遍所有元素所在的DOM树，
    直到遇到了一个跟提供的参数匹配的元素的时候才会停下来。
    这个新jQuery对象里包含了下面所有找到的同辈元素，但不包括那个选择器匹配到的元素。
    如果没有选择器匹配到，或者没有提供参数，那么跟在后面的所有同辈元素都会被选中。这就跟用没有提供参数的 .nextAll()效果一样。
* 参数：
    * 1）[expr][,filter] String,String
        expr: 用于筛选祖先元素的表达式。
        expr: 用于筛选祖先元素的表达式。
        fliter: 一个字符串，其中包含一个选择表达式匹配元素。
    * 2）[element][,filter] DOMElement,String
        element: 用于筛选祖先元素的DOM元素。
        filter: 一个字符串，其中包含一个选择表达式匹配元素。

#### 17、 offsetParent() 返回第一个匹配元素用于定位的父节点
    这返回父元素中第一个其position设为relative或者absolute的元素。此方法仅对可见元素有效。
* 参数：
    * 1）无

#### 18、parent([expr]) 取得一个包含着所有匹配元素的[*最近的*]唯一父元素的元素集合。
    你可以使用可选的表达式来筛选。
* 参数：
    * 1）expr 用来筛选的表达式

#### 19、parents([expr]) 取得一个包含着所有匹配元素的祖先元素的元素集合（不包含根元素）。
    可以通过一个可选的表达式进行筛选。
* 参数：
    * 1）expr
        用于筛选祖先元素的表达式
    
#### 20、parentsUntil([expr|element][,filter]) 查找当前元素的所有的父辈元素，直到遇到匹配的那个元素为止。[1.6+]
    如果提供的jQuery代表了一组DOM元素，.parentsUntil()方法也能让我们找遍所有元素的祖先元素，
    直到遇到了一个跟提供的参数匹配的元素的时候才会停下来。
    这个返回的jQuery对象里包含了下面所有找到的父辈元素，但不包括那个选择器匹配到的元素。
* 参数：
    * 1）[expr][,filter] string,string
        expr: 用于筛选祖先元素的表达式
        filter: 一个字符串，其中包含一个选择表达式匹配元素。
    * 2）[element][,filter] domelement,string
        element:用于筛选祖先元素的DOM元素
        filter: 一个字符串，其中包含一个选择表达式匹配元素。
