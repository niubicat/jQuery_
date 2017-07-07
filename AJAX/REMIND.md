* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 三、AJAX部分

#### 1、jQuery.ajax(url,[settings]) 通过 HTTP 请求加载远程数据
    jQuery 底层 AJAX 实现。简单易用的高层实现见 $.get, $.post 等;
    $.ajax() 返回其创建的 XMLHttpRequest 对象;最简单的情况下，$.ajax()可以不带任何参数直接使用;
    所有的选项都可以通过$.ajaxSetup()函数来全局设置;
* 回调函数：beforeSend、error、dataFilter、success、complete
* 数据类型：XML，还可以指定 html、json、jsonp、script或者text
* 发送数据到服务器：GET/POST可以设定type，影响data，data:'key1=value1'或一个映射 {key1: 'value1', key2: 'value2'}
* 高级选项：global选项用于阻止响应注册的回调函数，比如.ajaxSend，或者ajaxError，以及类似的方法；
    比如发送的请求非常频繁且简短的时候，就可以在ajaxSend里禁用这个。
    http 认证，通过username和password设置；
    ajax限时请求，可通过jquery.ajaxSetup全局设置，timeout选项；
    禁止缓存，cache:false，自上次请求后没改变，报错，设置ifModified:true;
    scriptCharset，给script标签设置特定的字符集；
    async:true，异步请求；
* 参数：
    * 1）url,[settings]
            url:一个用来包含发送请求的URL字符串
            settings:AJAX 请求设置。所有选项都是可选的
    * 2）settings:选项
        * accepts:取决于数据类型，内容类型发送请求头，告诉服务器什么样的响应会接受返回。
            如果accepts设置需要修改，推荐在$.ajaxSetup()方法中做一次
        * async:(默认: true) 默认设置下，所有请求均为异步请求。
            如果需要发送同步请求，请将此选项设置为 false。
            注意，同步请求将锁住浏览器，用户其它操作必须等待请求完成才可以执行。
        * beforeSend(XHR对象):发送请求前可修改 XMLHttpRequest 对象的函数，如添加自定义 HTTP 头;
            XMLHttpRequest 对象是唯一的参数。这是一个 Ajax 事件。
            如果返回false可以取消本次ajax请求。
        * cache:(默认: true,dataType为script和jsonp时默认为false) jQuery 1.2 新功能，设置为 false 将不缓存此页面
        * complete(XHR, TS):请求完成后回调函数 (请求成功或失败之后均调用)。
            参数： XMLHttpRequest 对象和一个描述成功请求类型的字符串
        * contents:一个以"{字符串:正则表达式}"配对的对象，用来确定jQuery将如何解析响应，给定其内容类型
        * contentType:（默认："application/x-www-form-urlencoded"）发送信息至服务器时内容编码类型。
            如果你明确地传递了一个content-type给 $.ajax() 那么他必定会发送给服务器（即使没有数据要发送）
        * context:这个对象用于设置Ajax相关回调函数的上下文。
            也就是说，让回调函数内this指向这个对象
            （如果不设定这个参数，那么this就指向调用本次AJAX请求时传递的options参数）
            比如指定一个DOM元素作为context参数，这样就设置了success回调函数的上下文为这个DOM元素
        * converters:默认： {"* text": window.String, "text html": true, "text json": jQuery.parseJSON,            "text xml": jQuery.parseXML}
            一个数据类型对数据类型转换器的对象。每个转换器的值是一个函数，返回响应的转化值
        * crossDomain:默认： 同域请求为false;跨域请求为true如果你想强制跨域请求（如JSONP形式）同一域，
            设置crossDomain为true。例如，服务器端重定向到另一个域
        * data:发送到服务器的数据。[*将自动转换为请求字符串格式*]
           GET 请求中将附加在 URL 后。查看 processData 选项说明以禁止此自动转换。
           必须为 Key/Value 格式。如果为数组，jQuery 将自动为不同值对应同一个名称。
           如 {foo:["bar1", "bar2"]} 转换为 "&foo=bar1&foo=bar2" 
        * dataFiler:给Ajax返回的原始数据的进行预处理的函数。
            提供data和type两个参数：data是Ajax返回的原始数据，type是调用jQuery.ajax时提供的dataType参数。
            函数返回的值将由jQuery进一步处理。
        * dataType:预期服务器返回的数据类型，如果不指定，jQuery 将自动根据 HTTP 包 MIME 信息来智能判断
            比如XML MIME类型就被识别为XML。在1.4中，JSON就会生成一个JavaScript对象，而script则会执行这个脚本。
            随后服务器端返回的数据会根据这个值解析后，传递给回调函数。
            * "xml": 返回 XML 文档，可用 jQuery 处理
            * "html": 返回纯文本 HTML 信息；包含的script标签会在插入dom时执行
            * "script": 返回纯文本 JavaScript 代码。不会自动缓存结果。
                除非设置了"cache"参数。注意：在远程请求时(不在同一个域下)，所有POST请求都将转为GET请求。
                (因为将使用DOM的script标签来加载)
            * "json": 返回 JSON 数据
            * "jsonp": JSONP 格式。使用 JSONP 形式调用函数时，
                如 "myurl?callback=?" jQuery 将自动替换 ? 为正确的函数名，以执行回调函数
            * "text": 返回纯文本字符串
        * error:(默认: 自动判断 (xml 或 html)) 请求失败时调用此函数
            有以下三个参数：XMLHttpRequest 对象、错误信息、（可选）捕获的异常对象。
            如果发生了错误，错误信息（第二个参数）除了得到null之外，
            还可能是"timeout", "error", "notmodified" 和 "parsererror"
        * global:(默认: true) 是否触发全局 AJAX 事件。
            设置为 false 将不会触发全局 AJAX 事件，如 ajaxStart 或 ajaxStop
        * headers:Default: {} 一个额外的"{键:值}"对映射到请求一起发送。
            此设置被设置之前beforeSend函数被调用;因此，消息头中的值设置可以在覆盖beforeSend函数范围内的任何设置
        * ifModified:(默认: false) 仅在服务器数据改变时获取新数据
            使用 HTTP 包 Last-Modified 头信息判断。在jQuery 1.4中，他也会检查服务器指定的'etag'来确定数据没有被修改过
        * isLocal:默认: 取决于当前的位置协议，允许当前环境被认定为“本地”，（如文件系统），即使jQuery默认情况下不会承认它
            以下协议目前公认为本地：file, *-extension, and widget
            如果isLocal设置需要修改，建议在$.ajaxSetup()方法中这样做一次
        * jsonp:在一个jsonp请求中重写回调函数的名字。
            这个值用来替代在"callback=?"这种GET或POST请求中URL参数里的"callback"部分
            比如{jsonp:'onJsonPLoad'}会导致将"onJsonPLoad=?"传给服务器
        * jsonpCallback:为jsonp请求指定一个回调函数名;
            这个值将用来取代jQuery自动生成的随机函数名。
            这主要用来让jQuery生成度独特的函数名，这样管理请求更容易，也能方便地提供回调函数和错误处理。
            你也可以在想让浏览器缓存GET请求的时候，指定这个回调函数名
        * mimeType:一个mime类型用来覆盖XHR的 MIME类型
        * password:用于响应HTTP访问认证请求的密码
        * processData:(默认: true) 默认情况下，通过data选项传递进来的数据
            如果是一个对象(技术上讲只要不是字符串)，都会处理转化成一个查询字符串
            以配合默认内容类型 "application/x-www-form-urlencoded"。
            如果要发送 DOM 树信息或其它不希望转换的信息，请设置为 false。
        * scriptCharset:只有当请求时dataType为"jsonp"或"script"，并且type是"GET"才会用于强制修改charset。
            通常只在本地和远程的内容编码不同时使用
        * statusCode:默认: {} 一组数值的HTTP代码和函数对象，当响应时调用了相应的代码
        * success(data, textStatus, jqXHR):请求成功后的回调函数。
            参数：由服务器返回，并根据dataType参数进行处理后的数据；描述状态的字符串。还有 jqXHR（XMLHttpRequest） 对象 
            成功设置可以接受一个函数数组。每个函数将被依次调用
        * traditional:如果你想要用传统的方式来序列化数据，那么就设置为true。请参考jQuery.param 方法
        * timeout:设置请求超时时间（毫秒）。此设置将覆盖全局设置
        * type:(默认: "GET") 请求方式 ("POST" 或 "GET")， 默认为 "GET"。
            注意：其它 HTTP 请求方法，如 PUT 和 DELETE 也可以使用，但仅部分浏览器支持。
        * url:(默认: 当前页地址) 发送请求的地址
        * username:用于响应HTTP访问认证请求的用户名
        * xhr:需要返回一个XMLHttpRequest 对象。默认在IE下是ActiveXObject 而其他情况下是XMLHttpRequest
            用于重写或者提供一个增强的XMLHttpRequest 对象
        * xhrFields:一对“文件名-文件值”在本机设置XHR对象。
            你可以用它来设置withCredentials为true的跨域请求

#### 2、load(url, [data], [callback]) 载入远程 HTML 文件代码并插入至 DOM 中
    默认使用 GET 方式 - 传递附加参数时自动转换为 POST 方式。
    可以指定选择符，来筛选载入的 HTML 文档，DOM 中将仅插入筛选出的 HTML 代码。语法形如 "url #some > selector"。
* 参数：
    * 1）url,[data,[callback]]
        url:待装入 HTML 网页网址
        data:发送至服务器的 key/value 数据
        callback:载入成功时回调函数

#### 3、jQuery.get(url, [data], [callback], [type]) 通过远程 HTTP GET 请求载入信息
    这是一个简单的 GET 请求功能以取代复杂 $.ajax 。请求成功时可调用回调函数。如果需要在出错时执行函数，请使用 $.ajax
* 参数：
    * 1）url,[data],[callback],[type]
        url:待载入页面的URL地址
        data:待发送 Key/value 参数
        callback:载入成功时回调函数
        type:返回内容格式，xml, html, script, json, text, _default

#### 4、jQuery.getJSON(url, [data], [callback]) 通过 HTTP GET 请求载入 JSON 数据
    使用JSONP形式的回调函数来加载其他网域的JSON数据，如 "myurl?callback=?"。
    jQuery 将自动替换 ? 为正确的函数名，以执行回调函数。 注意：此行以后的代码将在这个回调函数执行前执行        
* 参数：
    * 1）url,[data],[callback]
        url:发送请求地址
        data:待发送 Key/value 参数
        callback:载入成功时回调函数

#### 5、jQuery.getScript(url, [callback]) 通过 HTTP GET 请求载入并执行一个 JavaScript 文件
    jQuery 1.2 版本之前，getScript 只能调用同域 JS 文件。
    1.2中，您可以跨域调用 JavaScript 文件。
    注意：Safari 2 或更早的版本不能在全局作用域中同步执行脚本。
    如果通过 getScript 加入脚本，请加入延时函数
* 参数：
    * 1）url,[callback]
        url:待载入 JS 文件地址
        callback:成功载入后回调函数

#### 6、jQuery.post(url, [data], [callback], [type]) 通过远程 HTTP POST 请求载入信息
    这是一个简单的 POST 请求功能以取代复杂 $.ajax 。
    请求成功时可调用回调函数。如果需要在出错时执行函数，请使用 $.ajax；
    jQuery 1.12 中 jQuery.post 和 jQuery.get 支持对象参数，这样一来好处还比较多
    比如设置回调函数的context，或者跨域 post 时可以withCredential: true
* 参数：
    * 1）url,[data],[callback],[type]
        url:发送请求地址
        data:待发送 Key/value 参数
        callback:发送成功时回调函数
        type:返回内容格式，xml, html, script, json, text, _default

#### 7、ajaxComplete(callback) AJAX 请求完成时执行函数。Ajax 事件
    XMLHttpRequest 对象和设置作为参数传递给回调函数
* 参数：
    * 1）callback

#### 8、ajaxError(callback) AJAX 请求发生错误时执行函数。Ajax 事件
    XMLHttpRequest 对象和设置作为参数传递给回调函数。
    捕捉到的错误可作为最后一个参数传递
* 参数：
    * 1）callback

#### 9、ajaxSend(callback) AJAX 请求发送前执行函数。Ajax 事件
    XMLHttpRequest 对象和设置作为参数传递给回调函数
* 参数：
    * 1）callback

#### 10、ajaxStart(callback) AJAX 请求开始时执行函数。Ajax 事件
* 参数：
    * 1）callback

#### 11、ajaxStop(callback) AJAX 请求结束时执行函数。Ajax 事件
* 参数：
    * 1）callback

#### 12、ajaxSuccess(callback) AJAX 请求成功时执行函数。Ajax 事件
* 参数：
    * 1）callback

#### 13、jQuery.ajaxPrefilter( [dataTypes] , handler(options, originalOptions, jqXHR) )
    用于指定预先处理Ajax参数选项的回调函数
* 参数：
    * 1）dataTypes
    * 2）callback

#### 14、jQuery.ajaxSetup([options]) 设置全局 AJAX 默认选项
* 参数：
    * 1）options
        选项设置
    
#### 15、serialize() 序列表表格内容为字符串
* 参数：
     * 1）无

#### 16、serializeArray() 序列化表格元素 (类似 '.serialize()' 方法) 返回 JSON 数据结构数据
    注意: 此方法返回的是JSON对象而非JSON字符串。需要使用插件或者第三方库进行字符串化操作
    返回的JSON对象是由一个对象数组组成的，其中每个对象包含一个或两个名值对——name参数和value参数（如果value不为空的话）
* 参数：
    * 1）无
    