# drow
drow（卓尔），也就是黑暗精灵哦，这就是我们的后台框架了。

drow是在express基础上进一步封装的后台框架。

drow将渲染和逻辑彻底分离开了，渲染就是view部分，逻辑模块通过renderparam去影响view，view通过ctrl来影响逻辑模块。

drow还会有一套现成的用户管理模块，通用的后台管理员权限管理。

基本概念：
---
* session：每个连接的数据记录，session是支持复杂JSON对象的，所以不同模块有不同的模块节点
* renderparam：这个是用来实现mod和view之间交互的，这个也是支持复杂JSON对象的，也按模块来分
* module：就是一个纯逻辑模块单元，一般来说，这个模块单元主要用于复用，遵循一定规则，具体的模块大类还是会单独写的，这个模块只是一个中间层
* view：目前就是jade模板，尽可能不要产生生成cache的jade内容，而尽可能用文件方式组合
* page：页面，理论上来说，一个请求就是一个页面，不过这里的页面可以通过路由支持一组请求
* ctrl：一般这里表示ajax请求，基于一个页面规则的，ctrl返回的必然是json对象
* requestinfo：每个请求会有一个请求信息，所有mod、ctrl其实都是操作这个requestinfo的

更新说明：
---

> ver 0.1.0
> 
> * 基本框架搭建
> * 基本的命令行工具


使用到的第三方库
---

* 使用[express](http://expressjs.com/)做最底层的web服务
* 使用[Handlebars](http://handlebarsjs.com/)模板引擎来生成基本项目