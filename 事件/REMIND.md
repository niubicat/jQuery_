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
        
#### 3、off(event,[selector],[fn]) 在选择元素上移除一个或多个事件的事件处理函数。[1.7+]
    off() 方法移除用.on()绑定的事件处理程序。特定的事件处理程序可以被移除元素上提供事件的名称，
    命名空间，选择器，或处理函数名称的组合。
    当有多个过滤参数，所提供的参数都必须匹配的事件处理程序被删除。
    1、如果一个简单的事件名称，比如提供"click"，所有 这种类型的事件（包括直接和委派）从jQuery设置的元素上删除。
    2、当编写代码，将作为一个插件使用，或者干脆当一个大的代码基础工作，最好的做法是安装和取下使用命名空间的事件，
        从而使代码不会无意中删除其他代码附加事件处理程序。在一个特定的命名空间中的所有类型的所有事件，
        可以从一个元素中删除，只是提供了一个命名空间，比如 ".myPlugin"。至少，无论是命名空间或事件名称必须提供。
    3、要删除特定的委派事件处理程序，提供一个selector 的参数。选择器字符串必须是完全匹配递到.on()事件处理程序附加的选择器。
        要删除非委托元素上的所有事件，使用特殊值 "**" 。
    4、处理程序也可以删除handler参数指定名称的函数。当jQuery的绑定一个事件处理程序，它分配一个唯一的ID给处理函数。
    5、函数用jQuery.proxy()代理或类似有相同的唯一ID机制（代理函数），
        因此，通过代理处理程序.off 可能会删除比预期更多的处理程序。
        在这些情况下，最好是附加和移除事件处理程序，使用命名空间。
    6、和.on()一样，你可以传递一个 events-map>参数明确的指定而不是用events 和 handler作为单独参数。
        键事件和/或命名空间;值是处理函数或为false的特殊价值。
* 参数：
    * 1）events,[selector],[fn]
        events:一个或多个空格分隔的事件类型和可选的命名空间，
            或仅仅是命名空间，比如"click", "keydown.myPlugin", 或者 ".myPlugin".
        selector:一个最初传递到.on()事件处理程序附加的选择器。
        fn:事件处理程序函数以前附加事件上，或特殊值false.
    * 2）events-map,[selector]
        events-map:一个用字符串表示的，一个或多个空格分隔的事件类型和可选的命名空间，值表示先前事件绑定的处理函数。
        selector:一个最初传递到.on()事件处理程序附加的选择器。

#### 4、bind(type,[data],fn) 为每个匹配元素的特定事件绑定事件处理函数。[3.0-]
    jQuery 3.0中已弃用此方法，请用 on()代替。
* 参数：
    * 1）type,[data],function(eventObject)
        type: 含有一个或多个事件类型的字符串，由空格分隔多个事件。比如"click"或"submit"，还可以是自定义事件名
        data:作为event.data属性值传递给事件对象的额外数据对象
        fn:绑定到每个匹配元素的事件上面的处理函数
    * 2）type,[data],false
        type:含有一个或多个事件类型的字符串，由空格分隔多个事件。比如"click"或"submit"，还可以是自定义事件名
        data:作为event.data属性值传递给事件对象的额外数据对象
        false: 将第三个参数设置为false会使默认的动作失效
    * 3）events
        一个或多个事件类型的字符串和函数的数据映射来执行他们

#### 5、one(type,[data],fn) 为每一个匹配元素的特定事件（像click）绑定一个【*一次性*】的事件处理函数。
    在每个对象上，这个事件处理函数只会被执行一次。其他规则与bind()函数相同。
    这个事件处理函数会接收到一个事件对象，可以通过它来阻止（浏览器）默认的行为。
    如果既想取消默认的行为，又想阻止事件起泡，这个事件处理函数必须返回false。
    多数情况下，可以把事件处理函数定义为匿名函数。
    在不可能定义匿名函数的情况下，可以传递一个可选的数据对象作为第二个参数（而事件处理函数则作为第三个参数）
* 参数：
    * 1）type,[data],fn 
        type:添加到元素的一个或多个事件。由空格分隔多个事件。必须是有效的事件
        data:将要传递给事件处理函数的数据映射
        data:将要传递给事件处理函数的数据映射

#### 6、trigger(type,[data]) 在每一个匹配的元素上触发某类事件
    这个函数也会导致浏览器同名的默认行为的执行
    比如，如果用trigger()触发一个'submit'，则同样会导致浏览器提交表单。如果要阻止这种默认行为，应返回false
    你也可以触发由bind()注册的自定义事件而不限于浏览器默认事件
    事件处理函数会收到一个修复的(规范化的)事件对象，但这个对象没有特定浏览器才有的属性，比如keyCode。
    jQuery也支持 <a href="http://docs.jquery.com/Namespaced_Events">命名空间事件</a>。
    这允许你触发或者解除绑定一组特定的事件处理函数，而无需一一个指定。
    你可以在事件类型后面加上感叹号 ! 来只触发那些没有命名空间的事件处理函数

    所有触发的事件现在会冒泡到DOM树上了。举例来说，如果你在一个段落p上触发一个事件，
    他首先会在这个元素上触发，其次到父元素，在到父元素的父元素，直到触发到document对象。
    这个事件对象有一个 .target 属性指向最开始触发这个事件的元素。
    你可以用 stopPropagation() 来阻止事件冒泡，或者在事件处理函数中返回false即可。
* 参数：
    * 1） type,[data]
        type:一个事件对象或者要触发的事件类型
        data:传递给事件处理函数的附加参数
    * 2）event
        事件发生时运行的函数

#### 7、triggerHandler(type, [data]) 这个特别的方法将会触发指定的事件类型上所有绑定的处理函数。
    但不会执行浏览器默认动作，也不会产生事件冒泡。
    这个方法的行为表现与trigger类似，但有以下三个主要区别：
    第一，他不会触发浏览器默认事件
    第二，只触发jQuery对象集合中第一个元素的事件处理函数
    第三，这个方法的返回的是事件处理函数的返回值，而不是据有可链性的jQuery对象。
        此外，如果最开始的jQuery对象集合为空，则这个方法返回 undefined 

* 参数：
    * 1）type,[data]
        type:要触发的事件类型
        data:传递给事件处理函数的附加参数

#### 8、unbind(type,[data|fn]) bind()的反向操作，从每一个匹配的元素中删除绑定的事件。[3.0-]
    jQuery 3.0中已弃用此方法，请用 off()代替。
    如果没有参数，则删除所有绑定的事件
    你可以将你用bind()注册的自定义事件取消绑定
    如果提供了事件类型作为参数，则只删除该类型的绑定事件
    如果把在绑定时传递的处理函数作为第二个参数，则只有这个特定的事件处理函数会被删除。
*  参数：
    * 1）type,[fn] 
        type:删除元素的一个或多个事件,由空格分隔多个事件值
        fn:要从每个匹配元素的事件中反绑定的事件处理函数
    * 2）type,false
        type:删除元素的一个或多个事件,由空格分隔多个事件值
        false:设置为false会使默认的动作失效
    * 3）eventObject
        事件对象。这个 eventObj 参数来自事件绑定函数

#### 9、live(type,[data],fn) jQuery 给所有匹配的元素附加一个事件处理函数，即使这个元素是以后再添加进来的也有效 [1.7-]
    这个方法是基本是的 .bind() 方法的一个变体。
    使用 .bind() 时，选择器匹配的元素会附加一个事件处理函数，而以后再添加的元素则不会有。
    为此需要再使用一次 .bind() 才行。

    事件委托:
    .live() 方法能对一个还没有添加进DOM的元素有效，是由于使用了事件委托：
    绑定在祖先元素上的事件处理函数可以对在后代上触发的事件作出回应。
    传递给 .live() 的事件处理函数不会绑定在元素上，
    而是把他作为一个特殊的事件处理函数，绑定在 DOM 树的根节点上。

    当点击新的元素后，会依次发生下列步骤:
    1、生成一个click事件传递给 来处理
    2、由于没有事件处理函数直接绑定在 <divgt; 上，所以事件冒泡到DOM树上
    3、事件不断冒泡一直到DOM树的根节点，默认情况下上面绑定了这个特殊的事件处理函数
    4、执行由 .live() 绑定的特殊的 click 事件处理函数
    5、这个事件处理函数首先检测事件对象的 target 来确定是不是需要继续。
        这个测试是通过检测 $(event.target).closest('.clickme') 
        能否找到匹配的元素来实现的
    6、如果找到了匹配的元素，那么调用原始的事件处理函数

    附加说明:
    .live() 虽然很有用，但由于其特殊的实现方式，所以不能简单的在任何情况下替换 .bind()。
    主要的不同有：
    在jQuery 1.4中，.live()方法支持自定义事件，也支持所有的 JavaScript 事件。
    在jQuery 1.4.1中，甚至也支持 focus 和 blue 事件了（映射到更合适，并且可以冒泡的focusin和focusout上）。
    另外，在jQuery 1.4.1中，也能支持hover（映射到"mouseenter mouseleave"）。
    然而在jQuery 1.3.x中，只支持支持的JavaScript事件和自定义事件：
    click, dblclick, keydown, keypress, keyup, mousedown, 
    mousemove, mouseout, mouseover, 和 mouseup.

    .live() 并不完全支持通过DOM遍历的方法找到的元素。
    取而代之的是，应当总是在一个选择器后面直接使用 .live() 方法

    当一个事件处理函数用 .live() 绑定后，要停止执行其他的事件处理函数，
    那么这个函数必须返回 false。 仅仅调用 .stopPropagation() 无法实现这个目的。

    从 jQuery 1.7 开始，不再建议使用 .live() 方法。请使用 .on() 来添加事件处理。
    使用旧版本的用户，应该优先使用 .delegate() 来替代 .live()。
*  参数：
    * 1）type,[fn]
        type:一个或多个事件类型，由空格分隔多个事件
        fn:要从每个匹配元素的事件中反绑定的事件处理函数
    * 2）type,[data],false
        type:一个或多个事件类型，由空格分隔多个事件
        data:传递给事件处理函数的附加参数
        false:设置为false会使默认的动作失效
    * 3）event
        一个或多个事件类型的字符串和函数的数据映射来执行他们

#### 10、die(type,[fn]) 从元素中删除先前用.live()绑定的所有事件.(此方法与live正好完全相反。) [1.7-]
    如果不带参数，则所有绑定的live事件都会被移除。
    你可以解除用live注册的自定义事件。
    如果提供了type参数，那么会移除对应的live事件。
    如果也指定了第二个参数function,则只移出指定的事件处理函数。

    从 jQuery 1.7 开始，不再建议使用 .die() (以及它的互补方法 .live())。
    请使用 .off() 来代替，用于移除通过 .on() 绑定的事件处理。
* 参数：
    * 1）type,[fn]
        type:要移除的一个或多个事件处理程序。由空格分隔多个事件值。必须是有效的事件
        fn:要移除的函数
    * 2）type
        要移除的一个或多个事件处理程序。 由空格分隔多个事件值。必须是有效的事件。

#### 11、delegate(selector,[type],[data],fn) 指定的元素（属于被选元素的子元素）添加一个或多个事件处理程序[3.0-]
    并规定当这些事件发生时运行的函数
    jQuery 3.0中已弃用此方法，请用 on()代替。
    使用 delegate() 方法的事件处理程序适用于当前或未来的元素（比如由脚本创建的新元素）
* 参数：
    * 1） selector,[type],fn
        selector:使用 delegate() 方法的事件处理程序适用于当前或未来的元素（比如由脚本创建的新元素）
        type:附加到元素的一个或多个事件。 由空格分隔多个事件值。必须是有效的事件
        fn:当事件发生时运行的函数
    * 2）selector,[type],[data],fn
        selector:选择器字符串，用于过滤器触发事件的元素
        type:附加到元素的一个或多个事件。由空格分隔多个事件值。必须是有效的事件
        data:传递到函数的额外数据
        fn:当事件发生时运行的函数
    * 3）selector,events
        selector:选择器字符串，用于过滤器触发事件的元素
        events:一个或多个事件类型的字符串和函数的数据映射来执行他们

#### 12、undelegate(selector,[type],fn) 删除由 delegate() 方法添加的一个或多个事件处理程序。[3.0-]
    jQuery 3.0中已弃用此方法，请用 off()代替。
* 参数：
    * 1）selector,[type]
        selector:需要删除事件处理程序的选择器
        type:需要删除处理函数的一个或多个事件类型。 由空格分隔多个事件值。必须是有效的事件。
    * 2）selector,[type],fn
        selector:需要删除事件处理程序的选择器
        type:需要删除处理函数的一个或多个事件类型。 由空格分隔多个事件值。必须是有效的事件
        fn:要删除的具体事件处理函数
    * 3） selector,events
        selector:需要删除事件处理程序的选择器
        events:一个或多个事件类型的字符串和函数的数据映射来执行他们。
    * 4） namepspace
        namespace:一个字符串，其中包含一个命名空间取消绑定的所有事件

#### 13、hover([over],out) 个模仿悬停事件（鼠标移动到一个对象上面及移出这个对象）的方法
    这是一个自定义的方法，它为频繁使用的任务提供了一种“保持在其中”的状态
    当鼠标移动到一个匹配的元素上面时，会触发指定的第一个函数。当鼠标移出这个元素时，会触发指定的第二个函数。
    而且，会伴随着对鼠标是否仍然处在特定元素中的检测（例如，处在div中的图像），
    如果是，则会继续保持“悬停”状态，而不触发移出事件（修正了使用mouseout事件的一个常见错误）
*  参数：
    * 1）over,out
        over:鼠标移到元素上要触发的函数
        out:鼠标移出元素要触发的函数
    * 2）out
        当鼠标移到元素上或移出元素时触发执行的事件函数
    
#### 14、toggle([speed],[easing],[fn]) 用于绑定两个或多个事件处理器函数，以响应被选元素的轮流的 click 事件
    如果元素是可见的，切换为隐藏的；如果元素是隐藏的，切换为可见的
    1.9版本 .toggle(function, function, … ) 方法删除,jQuery Migrate（迁移）插件可以恢复此功能
* 参数：
    * 1）[speed],[fn]
        speed: 隐藏/显示 效果的速度。默认是 "0"毫秒。可能的值：slow，normal，fast。
        fn:在动画完成时执行的函数，每个元素执行一次。
    * 2）[speed],[easing],[fn]
        speed: 隐藏/显示 效果的速度。默认是 "0"毫秒。可能的值：slow，normal，fast。
        easing:(Optional) 用来指定切换效果，默认是"swing"，可用参数"linear"
        fn:在动画完成时执行的函数，每个元素执行一次
    * 3）switch
        用于确定显示/隐藏的开关。如：true - 显示元素，false - 隐藏元素

#### 15、blur([[data],fn]) 当元素失去焦点时触发 blur 事件 
    这个函数会调用执行绑定到blur事件的所有函数，包括浏览器的默认行为
    可以通过返回false来防止触发浏览器的默认行为。blur事件会在元素失去焦点的时候触发，既可以是鼠标行为，也可以是按tab键离开的
* 参数：
    * 1）fn 
        在每一个匹配元素的blur事件中绑定的处理函数
    * 2）[data],fn
        data:blur([Data], fn) 可传入data供函数fn处理
        fn:在每一个匹配元素的blur事件中绑定的处理函数

#### 16、change([[data],fn]) 当元素的值发生改变时，会发生 change 事件
    该事件仅适用于文本域（text field），以及 textarea 和 select 元素。
    当用于 select 元素时，change 事件会在选择某个选项时发生。
    当用于 text field 或 text area 时，该事件会在元素失去焦点时发生。
* 参数：
    * 1）fn
        在每一个匹配元素的change事件中绑定的处理函数
    * 2）[data],fn
        data:change([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的change事件中绑定的处理函数。

#### 17、click([[data],fn]) 触发每一个匹配元素的click事件。
    这个函数会调用执行绑定到click事件的所有函数。
*  参数：
    * 1）fn
        在每一个匹配元素的click事件中绑定的处理函数。
    * 2）[data],fn
        data:click([Data], fn) 可传入data供函数fn处理
        fn:在每一个匹配元素的click事件中绑定的处理函数。

#### 18、dblclick([[data],fn]) 当双击元素时，会发生 dblclick 事件。
    当鼠标指针停留在元素上方，然后按下并松开鼠标左键时，就会发生一次 click。
    在很短的时间内发生两次 click，即是一次 double click 事件。
    提示：如果把 dblclick 和 click 事件应用于同一元素，可能会产生问题。
* 参数：
    * 1）fn
        在每一个匹配元素的dblclick事件中绑定的处理函数。
    * 2）[data],fn
        data:dblclick([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的dblclick事件中绑定的处理函数。

#### 19、error([[data],fn]) 当元素遇到错误（没有正确载入）时，发生 error 事件。
    这个函数会调用所有绑定到error事件上的函数，包括在对应元素上的浏览器默认行为。
    可以通过在某个绑定的函数中返回false来防止触发浏览器的默认行为。
    error事件通常可以在元素由于点击或者tab导航失去焦点时触发。

    对于error事件，没有一个公众的标准。在大多数浏览器中，当页面的JavaScript发生错误时，window对象会触发error事件;
    当图像的src属性无效时，比如文件不存在或者图像数据错误时，也会触发图像对象的error事件。

    如果异常是由window对象抛出，事件处理函数将会被传入三个参数：
    1、描述事件的信息 ("varName is not defined", "missing operator in expression", 等等.)
    2、包含错误的文档的完整URL
    3、异常发生的行数 如果事件处理函数返回true，则表示事件已经被处理，浏览器将认为没有异常。
* 参数：
    * 1）fn
        在每一个匹配元素的error事件中绑定的处理函数。
    * 2）[data],fn
        data:error([Data], fn) 可传入data供函数fn处理
        fn:在每一个匹配元素的error事件中绑定的处理函数。

#### 20、focus([[data],fn]) 当元素获得焦点时，触发 focus 事件
    可以通过鼠标点击或者键盘上的TAB导航触发。
    这将触发所有绑定的focus函数，注意，某些对象不支持focus方法。
* 参数：
    * 1）fn
        在每一个匹配元素的focus事件中绑定的处理函数。
    * 2）[data],fn
        data:focus([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的focus事件中绑定的处理函数。

#### 21、focusin([data],fn) 当元素获得焦点时，触发 focusin 事件。
    focusin事件跟focus事件区别在于，他可以在父元素上检测子元素获取焦点的情况。
* 参数：
    * 1）fn 在每一个匹配元素的focusin事件中绑定的处理函数
    * 2）[data],fn
        data:focusin([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的focusin事件中绑定的处理函数。

#### 22、focusout([data],fn) 当元素失去焦点时触发 focusout 事件
    focusout事件跟blur事件区别在于，他可以在父元素上检测子元素失去焦点的情况。
* 参数：
    * 1）fn
        在每一个匹配元素的focusout事件中绑定的处理函数。
    * 2）[data],fn
        data:focusout([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的focusout事件中绑定的处理函数

#### 23、keydown([[data],fn]) 当键盘或按钮被按下时，发生 keydown 事件
    注释：如果在文档元素上进行设置，则无论元素是否获得焦点，该事件都会发生。
* 参数：
    * 1）fn
        在每一个匹配元素的keydown事件中绑定的处理函数。
    * 2）[data],fn
        data:keydown([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的keydown事件中绑定的处理函数。

#### 24、keypress([[data],fn]) 当键盘或按钮被按下时，发生 keypress 事件。
    keypress 事件与 keydown 事件类似。当按钮被按下时，会发生该事件。
    它发生在当前获得焦点的元素上。
    不过，与 keydown 事件不同，每插入一个字符，就会发生 keypress 事件。
    注释：如果在文档元素上进行设置，则无论元素是否获得焦点，该事件都会发生。
* 参数：
    * 1）fn
        在每一个匹配元素的keypress事件中绑定的处理函数。
    * 2）[data],fn
        data:keypress([Data], fn) 可传入data供函数fn处理
        fn:在每一个匹配元素的keypress事件中绑定的处理函数。

#### 25、keyup([[data],fn]) 当按钮被松开时，发生 keyup 事件。
    它发生在当前获得焦点的元素上。  
    注释：如果在文档元素上进行设置，则无论元素是否获得焦点，该事件都会发生。
* 参数：
    * 1）fn 
        在每一个匹配元素的keyup事件中绑定的处理函数。
    * 2）[data],fn
        data:keyup([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的keyup事件中绑定的处理函数。

#### 26、mousedown([[data],fn]) 当鼠标指针移动到元素上方，并按下鼠标按键时，会发生 mousedown 事件。
    mousedown 与 click 事件不同，mousedown 事件仅需要按键被按下，而不需要松开即可发生。
* 参数：
    * 1）fn
        在每一个匹配元素的mousedown事件中绑定的处理函数。
    * 2）[data],fn
        data:mousedown([Data], fn) 可传入data供函数fn处理
        fn:在每一个匹配元素的mousedown事件中绑定的处理函数

#### 27、mouseenter([[data],fn]) 当鼠标指针穿过元素时，会发生 mouseenter 事件。
    该事件大多数时候会与mouseleave 事件一起使用。
    与 mouseover 事件不同，只有在鼠标指针穿过被选元素时，才会触发 mouseenter 事件。
    如果鼠标指针穿过任何子元素，同样会触发 mouseover 事件。
* 参数：
    * 1）fn
        在每一个匹配元素的mouseenter事件中绑定的处理函数。
    * 2）[data],fn
        data:mouseenter([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mouseenter事件中绑定的处理函数。

#### 28、mouseleave([[data],fn]) 当鼠标指针离开元素时，会发生 mouseleave 事件。
    该事件大多数时候会与mouseenter 事件一起使用。
    与 mouseout 事件不同，只有在鼠标指针离开被选元素时，才会触发 mouseleave 事件。
    如果鼠标指针离开任何子元素，同样会触发 mouseout 事件。
* 参数：
    * 1）fn
        在每一个匹配元素的mouseleave事件中绑定的处理函数。
    * 2）[data],fn
        data:mouseleave([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mouseleave事件中绑定的处理函数。

#### 29、mousemove([[data],fn]) 当鼠标指针在指定的元素中移动时，就会发生 mousemove 事件。
    mousemove事件处理函数会被传递一个变量——事件对象，其.clientX 和 .clientY 属性代表鼠标的坐标
* 参数：
    * 1）fn
        在每一个匹配元素的mousemove事件中绑定的处理函数。
    * 2）[data],fn 
        data:mousemove([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mousemove事件中绑定的处理函数。

#### 30、mouseout([[data],fn]) 当鼠标指针从元素上移开时，发生 mouseout 事件。
    注释：与 mouseleave 事件不同，不论鼠标指针离开被选元素还是任何子元素，都会触发 mouseout 事件。
    只有在鼠标指针离开被选元素时，才会触发 mouseleave 事件。
* 参数：
    * 1）fn
        在每一个匹配元素的mouseout事件中绑定的处理函数。
    * 2） [data],fn
        data:mouseout([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mouseout事件中绑定的处理函数。
    
#### 31、mouseover([[data],fn]) 当鼠标指针位于元素上方时，会发生 mouseover 事件。
    该事件大多数时候会与 mouseout 事件一起使用。
    注释：与 mouseenter 事件不同，不论鼠标指针穿过被选元素或其子元素，都会触发 mouseover 事件。
    只有在鼠标指针穿过被选元素时，才会触发 mouseenter 事件。
* 参数：
    * 1）fn 
        在每一个匹配元素的mouseover事件中绑定的处理函数。
    * 2）[data],fn
        data:mouseover([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mouseover事件中绑定的处理函数。

#### 32、mouseup([[data],fn]) 当在元素上放松鼠标按钮时，会发生 mouseup 事件。
    与 click 事件不同，mouseup 事件仅需要放松按钮。当鼠标指针位于元素上方时，放松鼠标按钮就会触发该事件。
* 参数：
    * 1）fn
        在每一个匹配元素的mouseup事件中绑定的处理函数。
    * 2）[data],fn
        data:mouseup([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的mouseup事件中绑定的处理函数。

#### 33、resize([[data],fn]) 当调整浏览器窗口的大小时，发生 resize 事件。
* 参数：
    * 1）fn
        在每一个匹配元素的resize事件中绑定的处理函数。
    * 2）[data],fn
        data:resize([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的resize事件中绑定的处理函数。

#### 34、scroll[[data],fn] 当用户滚动指定的元素时，会发生 scroll 事件。
    scroll 事件适用于所有可滚动的元素和 window 对象（浏览器窗口）。
* 参数：
    * 1）fn
        在每一个匹配元素的scroll事件中绑定的处理函数。
    * 2）[data],fn
        data:scroll([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的scroll事件中绑定的处理函数。
    
#### 35、select([[data],fn]) 当 textarea 或文本类型的 input 元素中的文本被选择时，会发生 select 事件。
    这个函数会调用执行绑定到select事件的所有函数，包括浏览器的默认行为。
    可以通过在某个绑定的函数中返回false来防止触发浏览器的默认行为。
* 参数：
    * 1）fn
        在每一个匹配元素的select事件中绑定的处理函数。
    * 2）[data],fn 
        data:select([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的select事件中绑定的处理函数。

#### 36、submit([[data],fn]) 当提交表单时，会发生 submit 事件。
    该事件只适用于表单元素。
* 参数：
    * 1）fn
        在每一个匹配元素的submit事件中绑定的处理函数。
    * 2）[data],fn
        data:submit([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的submit事件中绑定的处理函数。

#### 37、unload([[data],fn]) 在当用户离开页面时，会发生 unload 事件。
    具体来说，当发生以下情况时，会发出 unload 事件：
    1、点击某个离开页面的链接
    2、在地址栏中键入了新的 URL
    3、使用前进或后退按钮
    4、关闭浏览器
    5、重新加载页面
* 参数：
    * 1）fn
        在每一个匹配元素的unload事件中绑定的处理函数
    * 2）[data],fn
        data:unload([Data], fn) 可传入data供函数fn处理。
        fn:在每一个匹配元素的unload事件中绑定的处理函数。
        








