** http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html **
** http://www.css88.com/jqapi-1.9/ **
** https://oscarotero.com/jquery/ **
** http://www.365mini.com/diy.php?f=jquery-selector-demo ** 
### 一、核心部分
####1、jQuery([selector,[context]]) 
参数：	1) selector,[context]
		2) element
		3) object
		4) elementArray
		5) jquery object
		6) jquery() 
####2、jQuery(html,[ownerDocument]) [1.8+]
参数： 	1）html,[ownerDocument]
		2）html,props
####3、jQuery(callback) == $(document).ready()的简写
参数：	1）callback
####4、jQuery.holdReady(hold) 暂停或恢复.ready() 事件的执行 [3.2-]
参数：	1）true
		2) false
####5、each(callback) 以每一个匹配的元素作为上下文来执行一个函数
参数：	1）callback/Function
可以使用 'return false' 来提前跳出 each() 循环。
####6、size() jQuery 对象中元素的个数，当前匹配的元素个数，与length 将返回相同的值 [1.8-]
参数：	1）无
####7、length == size()属性，jQuery 对象中元素的个数
参数：	1）无
####8、selector 返回传给jQuery()的原始选择器，可以与context一起使用 [1.9-]
参数：	1）无
####9、context 返回传给jQuery()的原始的DOM节点内容，即jQuery()的第二个参数。如果没有指定，那么context指向当前的文档(document) [1.9-]
参数：	1）无
####10、get([index]) 取得其中一个匹配的元素。 num表示取得第几个匹配的元素。从0开始，返回的是DOM对象，类似的有eq(index),不过eq(index)返回的是jQuery对象。
参数：	1）[index]／选择一个实际的DOM 元素并且对他直接操作，而不是通过 jQuery 函数。$(this).get(0)与$(this)[0]等价
####11、index([selector|element]) 搜索匹配的元素，并返回相应元素的索引值，从0开始计数
参数：	1）index()
		2）selector 选择器，则返回值就是原先元素相对于选择器匹配元素中的位置
		3）element/DOM元素／一个或一组jquery对象
		4）无参，则返回第一个元素相对于其同辈元素的位置
####12、data([key],[value]) 在元素上存放或读取数据,返回jQuery对象; 只有一个key,读取该jQuery对象对应DOM中存储的key对应的值,
		同时可以读取该DOM中使用 data-[key] = [value] 所存储的值；
		当参数为两个时，为像该jQuery对象对应的DOM中存储key-value键值对的数据
参数：	1）key
		2）key，value
		3）obj 对象
		4）data()
####13、removeData([name|list]) 在元素上移除存放的数据，与 data([key], [value])函数作用相反 [1.7+]
参数：	1）[name] 数据key名
		2）[list] 数组／空格分开的字符串
####14、jQuery.data(element,[key],[value]) 在元素上存放数据,返回jQuery对象，一个底层方法。你应当使用.data()来代替 [1.8-]
参数：	1）element,key,value
			要关联数据的DOM对象，存储的数据名，存储的任意数据
		2）element,key
		3）element
####15、queue(element,[queueName]) 显示或操作在匹配元素上执行的函数队列
参数：	1）element,[queueName]
			element:检查附加列队的DOM元素
			queueName:字符串值，包含序列的名称。默认是 fx, 标准的效果序列
		2）element,queueName,newQueue
			element:检查附加列队的DOM元素
			queueName:字符串值，包含序列的名称。默认是 fx, 标准的效果序列。
			newQueue:替换当前函数列队内容的数组
		3）element,queueName,callback()
			element:检查附加列队的DOM元素
			queueName:字符串值，包含序列的名称。默认是 fx, 标准的效果序列。
			callback():要添加进队列的函数
####16、dequeue([queueName]) 从队列最前端移除一个队列函数，并执行他，或者终止一个自定义的队列函数
参数：	1）[queueName] 默认为fx
####17、clearQueue([queueName]) 清空对象上尚未执行的所有函数队列
			如果不带参数，则默认清空的是动画队列。这跟 stop(true)类似，
			但stop(true)只能清空动画队列，而这个可以清空所有通过 .queue() 创建的队列。
参数： 	1） queueName 
			队列名的字符串。默认是"Fx"，动画队列
####18、jQuery.fn.extend(object) 扩展 jQuery 元素集来提供新的方法（通常用来制作插件）
参数：	1）object（function）
			用来扩充 jQuery 对象的新函数
####19、jQuery.extend(object) 扩展jQuery对象本身，用来在jQuery命名空间上增加新函数
参数：	1) object
			用来扩充jQuery命名空间上的新函数
####20、jQuery.noConflict([extreme])  运行这个函数将变量$的控制权让渡给第一个实现它的那个库
			确保jQuery不会与其他库的$对象发生冲突，在运行这个函数后，就只能使用jQuery变量访问jQuery对象；$("div p")必须换成jQuery("div p")
			这个函数必须在你导入jQuery文件之后，并且在导入另一个导致冲突的库'''之前'''使用；
			当然也应当在其他冲突的库被使用之前，除非jQuery是最后一个导入的
参数：	1）extreme 
			true/false
			传入 true 来允许彻底将jQuery变量还原








