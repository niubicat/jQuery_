* [*jQuery API 中文文档*](http://jquery.cuishifeng.cn/jQuery_html_ownerDocument.html)
* [*jQuery API*](http://www.css88.com/jqapi-1.9/)
* [*jQuery Quick API Reference 3.0*](https://oscarotero.com/jquery/)
* [*jquery-demo在线*](http://www.365mini.com/diy.php?f=jquery-selector-demo)

### 十二、延迟对象

#### 1、deferred.done(doneCallbacks[,doneCallbacks]) 当延迟成功时调用一个函数或者数组函数
    该参数可以是一个函数或一个函数的数组。当延迟成功时，doneCallbacks被调用。
    回调执行是依照他们添加的顺序。
    一旦deferred.done()返回延迟对象，延迟对象的其它方法也可以链接到了这里，包括增加.done()方法。
    当延迟解决，doneCallbacks执行使用参数提供给resolve或resolveWith方法依照添加的顺序调用。
* 参数：
    * 1）doneCallbacks
        一个函数或者数组函数，延迟成功时调用
    * 2）doneCallbacks
        附加可选的函数或数组函数，延迟成功时调用

#### 2、deferred.fail(failCallbacks[,failCallbacks]) 当延迟失败时调用一个函数或者数组函数
    该参数可以是一个函数或一个函数的数组。当延迟失败时，doneCallbacks被调用。
    回调执行是依照他们添加的顺序。
    一旦deferred.fail()返回延迟对象，延迟对象的其它方法也可以链接到了这里，包括增加.done()方法。
    当延迟解决，doneCallbacks执行使用参数提供给resolve或resolveWith方法依照添加的顺序调用。
* 参数：
    * 1）failCallbacks
        一个函数或者数组函数，延迟失败时调用
    * 2）failCallbacks
        附加可选的函数或数组函数，延迟失败时调用

#### 3、deferred.isRejected() 确定延迟对象是否已被拒绝 [1.7-]
    jquery1.7API中已弃用，请用deferred.state()替代。
    如果延迟对象是在被拒绝的状态则返回true，
    这意味着要么deferred.reject()或者deferred.rejectWith()被调用的对象和failCallbacks被访问（或称正在这一进程中的）

    请注意，
    延迟的对象可以有三种状态：未解决（unresolved），解决（resolved），或拒绝（rejected）

    使用deferred.isResolved()来判断延迟对象是否在解决状态 。
    这些方法主要用于调试时非常有用，例如，以确定是否递延已经解决，即使你在代码中打算拒绝。
* 参数：
    * 1）无

#### 4、deferred.isResolved() 确定延迟对象是否已得到解决 [1.7-]
    jquery1.7API中已弃用，请用deferred.state()替代。
    如果延迟对象是在被解决的状态则返回true，
    这意味着要么deferred.resolved()或者deferred.resolveWith()被调用的对象
    和failCallbacks被访问（或称正在这一进程中的）。

    请注意，延迟的对象可以有三种状态：未解决（unresolved），解决（resolved），或拒绝（rejected）;
    使用deferred.isResolved()来判断延迟对象是否在解决状态 。
    这些方法主要用于调试时非常有用，例如，以确定是否递延已经解决，即使你在代码中打算拒绝。
* 参数：
    * 1）无

#### 5、deferred.reject(args) 拒绝延迟对象，并根据给定的参数调用任何失败的回调函数
    当延迟被拒绝，任何failCallbacks添加的deferred.then或deferred.fail被调用。
    回调按他们添加的顺序执行。
    每个回调传递的args在deferred.reject()中调用。
    之后添加任何failCallbacks递延被拒绝进入状态时，立即执行添加，使用的参数被传递给.reject()调用。
* 参数：
    * 1）args
        传递给failCallbacks的可选参数。
    
#### 6、deferred.rejectWith(context, [args]) 拒绝延迟的对象，并根据给定的上下文和参数调用任何失败的回调函数
    当延迟被拒绝，任何doneCallbacks添加的deferred.then或deferred.fail被调用。回调按他们添加的顺序执行。
    每个回调传递的args在deferred.reject()中调用。
    之后添加任何failCallbacks递延被拒绝进入状态时，立即执行添加，使用的参数被传递给.reject()调用。
* 参数：
    * 1）args

#### 7、deferred.resolve(args) 解决递延对象，并根据给定的参数调用任何完成的回调函数
    当递延被解决，任何failCallbacks添加的deferred.then或deferred.done被调用。
    回调按他们添加的顺序执行。
    每个回调传递的args在deferred.resolve()中调用。
    之后添加任何failCallbacks递延被拒绝进入状态时，立即执行添加，使用的参数被传递给.resolve()调用。
* 参数：
    * 1）args
        传递给doneCallbacks的可选参数

#### 8、deferred.resolveWith(context, [args]) 解决递延对象，并根据给定的上下文和参数调用任何完成的回调函数
    当递延被解决，任何doneCallbacks 添加的deferred.then或deferred.done被调用。
    回调按他们添加的顺序执行。
    每个回调传递的args在deferred.resolveWith()中调用。
    之后添加任何failCallbacks递延被解决进入状态时，立即执行添加，使用的参数被传递给.resolveWith()调用。
* 参数：
    * 1）context
        上下文作为this对象传递给 doneCallbacks 
    * 2）args
        传递给doneCallbacks的可选参数

#### 9、deferred.then(doneFilter [,failFilter][,progressFilter])添加处理程序被调用时，递延对象得到解决或者拒绝[1.8+]
    所有三个参数（包括progressCallbacks ，在jQuery的1.7 ）可以是一个单独的函数或一个函数的数组。 
    其中一个参数，也可以为空，如果没有该类型的回调是需要的。
    或者，使用.done()或.fail()仅设置doneCallbacks或failCallbacks。

    当递延解决，doneCallbacks被调用。若递延代替拒绝，failCallbacks被调用。
    回调按他们添加的顺序执行。
    一旦deferred.then返回延迟对象，延迟对象的其它方法也可以链接到了这里，包括增加.then()方法。
* 参数：
    * 1）doneFilter[,failFilter][,progressFilter] 
        doneFilter: 当Deferred（延迟）对象得到解决时被调用的一个函数。
        failFilter: [可选]当Deferred（延迟）对象拒绝时被调用的一个函数。
        progressFilter:[可选]当Deferred（延迟）对象生成进度通知时被调用的一个函数。
    * 2）doneCallbacks,failCallbacks
        doneCallbacks: 一个函数或函数数组，当延迟成功时调用。
        failCallbacks: 一个函数或函数数组，当延迟失败时调用。
    * 3）doneCallbacks,failCallbacks[,progressCallbacks]
        doneCallbacks: 一个函数或函数数组，当延迟解决时调用。
        failCallbacks: 一个函数或函数数组，当延迟拒绝时调用。
        progressCallbacks: 一个可选的函数，当延迟对象通知进度（progress）时被调用。

#### 10、deferred.promise([type],[target]) 返回一个 Promise 对象用来观察当某种类型的所有行动绑定到集合，[1.6+]
    排队与否还是已经完成
    .promise()方法返回一个动态生成的Promise对象用来观察当某种类型的所有行动绑定到集合，排队与否还是已经完成。
    默认情况下， type是"fx" ，这意味着当选定的元素已完成所有动画是返回的Promise是解决的。
    解决上下文和唯一的参数是哪个集合到.promise()被调用。

    如果target是提供，.promise()将附加到它的方法，然后返回这个对象，而不是创建一个新的。
    这对在已经存在的对象上附加Promise的行为非常有用。
* 参数：
    * 1）type
        需要处理的字符串
    * 2）target  
        附有promise 方法的Object

#### 11、deferred.pipe([doneFilter][,failFilter][proressFilter]) 筛选器和/或链Deferreds的实用程序方法[1.8-]
    deferred.pipe()方法返回一个新的promise，该过滤器通过一个函数有关的递延状态和价值。
    该doneFilter和failFilter原递延过滤功能的解决/拒绝的状态和价值。
    这些过滤器函数可以返回一个新的值被传递给管道承诺的done()或fail()的回调，
    或者他们可以返回另一个观察对象（推迟，承诺等），将通过它的解决/拒绝状态和价值，以保证管道的回调。
    如果使用的是过滤功能null ，或不指定，则管道的承诺将得到解决或原驳回值具有相同。

    注意：从 jQuery 1.8 开始，deferred.pipe() 方法过时. 应该使用deferred.then() 代替它。
* 参数：
    * 1）doneFilter,failFilter
        doneFilter:可选函数，当递延得到解决时调用。
        failFilter:可选函数，当递延得被拒绝时调用。
    * 2）doneFilter,failFilter,progressFilter

#### 12、deferred.always(alwaysCallbacks[,alwaysCallbacks]) 当递延对象是解决或拒绝时被调用添加处理程序。[1.6+]
* 参数：
    * 1）alwaysCallbacks
        一个函数，或者函数数组，当递延对象是解决或拒绝时被调用。
    * 2）alwaysCallbacks
        附加可选的一个函数，或者函数数组，当递延对象是解决或拒绝时被调用。
    
#### 13、deferred.notify(args) 调用一个给定args的递延对象上的进行中的回调 （progressCallbacks）[1.7+]
    通常情况下，只有一个递延的创建者，应调用此方法;
    你可以防止其他代码改变Deferred的状态或者通过deferred.promise()返回一个受限制的承诺对象报告状态

    当 deferred.notify 被访问， 任何progressCallbacks 可以通过访问deferred.then 或者 deferred.progress来添加。
    回调是在它们被添加的顺序执行。每次通过来自.notify()的args回调。
    任何.notify()后递延是解决或拒绝（或之后添加任何progressCallbacks ）被忽略。
* 参数：
    * 1）args
        可选参数传递到进行中的回调（progressCallbacks）
    
#### 14、deferred.notifyWith(context,[args])调用一个给定args的递延对象上的进行中的回调（progressCallbacks）[1.7+]
    当 deferred.notifyWith 被访问，任何progressCallbacks,
    可以通过访问deferred.then 或者 deferred.progress来添加。
    回调是在它们被添加的顺序执行。每次通过来自.notifyWith()的args回调。
    任何.notifyWith()后递延是解决或拒绝（或之后添加任何progressCallbacks ）被忽略。
* 参数：
    * 1）context
        上下文传递progressCallbacks此对象
    * 2）args
        可选参数传递到progressCallbacks。

#### 15、deferred.progress(progressCallbacks) 当Deferred对象时生成进度通知时添加被访问处理程序。[1.7+]
    这个参数可以是一个单一的功能或功能的阵列。
    当递延通过调用生成的进度通知notify或notifyWith，progressCallbacks 被访问。
    后来deferred.progress()返回Deferred对象。
    Deferred对象有方法可以链接到这一个。当递延解决或拒绝，进展回调将不再被调用。
* 参数：
    * 1）progressCallbacks
        一个函数或函数数组，被呼叫递延生成进度通知。

#### 16、deferred.state() 确定一个Deferred对象的当前状态。[1.7+] 
    deferred.state（）方法返回一个字符串，代表Deferred对象的当前状态。 
    Deferred对象可以在三种状态之一：
    1) pending: Deferred对象是尚未完成状态 (不是 "rejected" 或 "resolved").
    2) resolved: Deferred对象是在解决状态，这意味着，deferred.resolve() 
            或者 deferred.resolveWith()被对象访问和doneCallbacks被访问（或在被调用的过程中）。
    3) rejected: Deferred对象是在被拒绝的状态，这意味着，deferred.reject() 
            或者 deferred.rejectWith() 被对象访问和failCallbacks被访问（或在被调用的过程中）。

    这种方法主要是有用的调试，以确定的，例如，递延是否已经得到解决，即使你打算拒绝它的内部代码。
* 参数：
    * 1）无



