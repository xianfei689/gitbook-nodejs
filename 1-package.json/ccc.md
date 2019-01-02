# 1、package.json

package.json 文件解析 [ 编辑](https://gitee.com/zhouxianfei/zhouxf.front.doc/wikis/package.json%20%E6%96%87%E4%BB%B6%E8%A7%A3%E6%9E%90?parent=NodeJS)

### 介绍

> 每个项目的根目录下面，一般都有一个package.json文件，定义了这个项目所需要的各种模块，以及项目的配置信息（比如名称、版本、许可证等元数据）。

### package.json 字段介绍

* 必要字段

name: 它属于必须字段，在package.json中最重要的就是name和version字段，如果没有就无法install name和version一起组成的标识在假设中是唯一的。改变包应该同时改变version。 使用时，应注意以下三点:

> 1. 不要在name中包含js, node字样；
> 2. 这个名字最终会是URL的一部分，命令行的参数，目录名，所以不能以点号或下划1开头；
> 3. 这个名字可能在require\(\)方法中被调用，所以应该尽可能短；

version:同上，属于必须字段

* 可选字段
* description: 可选字段，它必须是字符串，帮助我们了解创建的包
* keywords: 可选字段，可以是字符串数组，比如javascript, nodejs
* homepage: 可选字段，项目官网的url。注意: 这和“url”不一样。如果你放一个“url”字段，registry会以为是一个跳转到你发布在其他地方的地址
* bugs: 可选字段，问题追踪系统的URL或邮箱地址；npm bugs用的上
* license: 指定一个许可证，让人知道使用的权利和限制的
* main: main字段配置一个文件名指向模块的入口程序

> 这里输入引用文本如果你包的名字叫foo，然后用户require\("foo"\)，main配置的模块的exports对象会被返回

* scripts: “scripts”是一个由脚本命令组成的hash对象，他们在包不同的生命周期中被执行

![&#x8F93;&#x5165;&#x56FE;&#x7247;&#x8BF4;&#x660E;](https://images.gitee.com/uploads/images/2018/1216/221025_32d47742_1422543.png)

> key是生命周期事件，value是要运行的命令，使用方式 yarn run dev 或者 npm run prd

* config: 可选对象 为一个obj，Config对象中的值在Scripts的整个周期中皆可用，专门用于给Scripts提供配置参数
* repository: 指定你的代码存放的地方
* dependencies: 指示当前包所依赖的其他包，版本格式可以是下面任一种:

![&#x8F93;&#x5165;&#x56FE;&#x7247;&#x8BF4;&#x660E;](https://images.gitee.com/uploads/images/2018/1216/221139_52c1f190_1422543.png)

* devDependencies: 可选字段

> 如果只需要下载使用某些模块，而不下载这些模块的测试和文档框架，放在devDependencies下面比较不错

* private: 可选字段，布尔值

> 如果private为true，npm会拒绝发布。这可以防止私有repositories不小心被发布出去

![&#x8F93;&#x5165;&#x56FE;&#x7247;&#x8BF4;&#x660E;](https://images.gitee.com/uploads/images/2018/1216/221235_8f09e19c_1422543.png)

* engines：指定node版本

在package.json 中的engines 节点 指定 依赖的nodejs 的版本号码

![&#x8F93;&#x5165;&#x56FE;&#x7247;&#x8BF4;&#x660E;](https://images.gitee.com/uploads/images/2018/1216/221340_ddf36ab1_1422543.png)

