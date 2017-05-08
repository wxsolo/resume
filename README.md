# 个人信息

 - 伍星/男/1990
 - 工作年限：3年
 - 期望职位：Web前端开发工程师
 - 期望城市：北京/长沙/远程
 - 本科/中南民族大学/计算机科学与技术
 - Github: [https://github.com/wxsolo](https://github.com/wxsolo)

---

# 联系方式

- 手机/微信：13545085829 （武汉手机号）
- Email：[wxsolo@outlook.com](wxsolo@outlook.com)

---

# 工作经历

## 就旅行网（jiulvxing.com）（2016年12月~至今）

### *PC版机票*

在此项目中负责搭建前端工程，业务上负责首页+航班搜索列表页。

此项目是在已有touch项目的基础上，利用已有数据接口逻辑，快速构建一套PC版机票全流程页面。

### *touch个人中心*

独立负责此项目，在已有的touch前端+Node工程中加入个人中心功能。

这个项目比较有难度的是支持用户直接在客户端预览剪裁图片成头像，然后再将裁剪完后的图片上传后端，可省去服务端存储原图和服务端裁剪。

touch端选择图片后使用[FileReader](https://developer.mozilla.org/zh-CN/docs/Web/API/FileReader)读取实现本地预览。截取使用canvas绘制截取区域然后[toDataURL](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL)，进一步通过[window.atob](https://developer.mozilla.org/zh-CN/docs/Web/API/WindowBase64/atob)+[Uint8Array](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)+[Blob](https://developer.mozilla.org/zh-CN/docs/Web/API/Blob) 转换回文件流供提交后端。

## 北京奈斯特尔信息技术有限公司（Nestia.com）（2016年8月~2016年12月）

### *新闻(News)栏目*

主导此项目，带领重构工程师，与pm、设计、后端沟通。帮助重构工程师掌握charles调试touch页面技巧。

此项目主要包括h5端新闻详情页+app端新闻详情嵌入页+运营端新闻编辑系统，运营端使用技术为webpack+react+react-router+amazeui。

项目中，遇到困难的点是在编辑器中插入不可编辑的商品卡片。元素设置了[contenteditable](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/contenteditable)的可编辑区域A中，需要插入一个不可编辑的卡片结构B，如果对卡片结构B设置contenteditable=fasle，会在删除了卡片结构B的前后内容时，会导致整个编辑器区域A不可编辑。解决办法为使用iframe作为容器，在卡片结构写入iframe内后，通过designMode设置iframe的整个文档不可编辑。


### *POI(基于定位的商店信息)收集App*

参与此项目，项目使用React Native构建，负责2/3的需求量。

这个项目中，遇到的问题是使用的地图[react-native-maps](https://github.com/airbnb/react-native-maps)组件在Android机型上点击"获取当前定位"会导致crash，搜索react-native-maps项目issues后找到解决方案，具体可见[react-native-maps/issues#497](https://github.com/airbnb/react-native-maps/issues/497)。

---

## 去哪儿网（qunar.com）（2014年2月~2016年8月）

### *国内机票航班搜索列表页react重构*

参与此项目，负责搜索框区域组件开发，项目技术栈为webpack+react+Redux。

此项目为部门第一个大型react线上实践项目，也是我第一次自底向上构建react组件。其中搜索区域的城市输入框，由可独立复用的input组件+热门城市组件+城市suggest组件构成。在开发期间帮助其他同事解决react相关问题。

### *携程商旅审批全流程项目*

负责此项目整体前端，前往上海携程出差2个月+，带领重构同事把控项目需求和进行任务分配。

本项目是携程与去哪儿合作的内部审批流程项目，技术上使用Qunar前后端分离方案，Java后端只提供纯JSON API ，前端采用jQuery + Express。

项目难点是，跨公司和跨地区出差与携程的产品开发合作项目，最后项目比原计划提前一周提测发布。

### *售后服务平台-客服电话条项目*

独立负责此项目前端开发，与后端讨论选型，框架搭建。

此项目为客服接打电话的辅助工具，需要监听通话状态，依赖双向实时通信，鉴于websocket的兼容性和后端对分布式的要求，前端选择了[sockjs](https://github.com/sockjs/sockjs-client)作为websocket兼容库。

此项目的难点为sockjs只是兼容库，没有socket.io拥有的便于业务开发的功能(如Namespaces和Rooms)。解决办法是在[sockjs/websocket-multiplex](https://github.com/sockjs/websocket-multiplex)基础上，设计了类似Namespaces和Rooms的功能的Webio项目，并将暴露的api形成文档。最后在此基础上对接业务，实现了电话条的响铃/接听/转接/三方/挂机/拨号等实时操作。

### 其他项目

跟踪并解决线上Node.js服务的内存泄露问题。

公司使用Node.js实践前后端分离开发后，线上部署的Express项目隔20-30天左右，会将机器内存(1GB)吃满，导致监控系统报警。

使用[node-memwatch](https://github.com/lloyd/node-memwatch)在测试环境中对项目进行压测，对获得的heapsnapshot文件进行分析，发现内存消耗异常的是日志服务log4js。研究发现，当日志备份配置为按文件数备份时，会导致大量的SlowBuffer申请，其不受V8的内存限制导致泄露。最后修改log4js的备份方式为按日期备份解决此问题。

---

# 技能清单

以下均为我熟练使用的技能

- 开发工具：MacBook/Webstrom/Zsh/Nginx/charles
- 开发言语：javascript/Node.js/HTML/CSS
- Web框架：Express
- 前端框架：React
- 前端工具：jQuery/Zepto/Npm/SaSS/Webpack/Handlebars
- 版本管理：Git

# 关于我
安静沉稳偏内向，也宅也爱玩，徒步进沙漠，骑行青海湖，珠峰大本营前做倒立。

# 致谢
感谢您花时间阅读我的简历，期待能有机会和您共事。
