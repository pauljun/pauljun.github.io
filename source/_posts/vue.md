---
title: vue-cli项目搭建
comments: true
categories: javascript
tag: vue
---
vue中文官网 https://cn.vuejs.org/
<!--more-->

#### 谷歌调试工具:dev-tools
1.github下载地址：[https://github.com/vuejs/vue-devtools](https://link.juejin.im/?target=https%3A%2F%2Fgithub.com%2Fvuejs%2Fvue-devtools)
2.下载好后进入vue-devtools-master工程  执行npm install ----->npm run build.
3.然后打开shells>chrome>src>manifest.json 把里面的"persistent": false改为true
4.打开谷歌浏览器设置--->扩展程序--》勾选开发者模式---》添加工程中的shells-->chrome的内容，至此恭喜已经安装成功！！！
5.打开自己的vue项目中，如果是有vue-cli构建的项目，执行npm run dev,打开http://localhost:8080/ 服务器调试地址；至此完成devtools的安装；
#### 利用vue-cli来初始化我们的项目
```
//全局安装webpack
npm install -g webpack

//安装vue-cli
npm install -g vue-cli

//使用vue-cli初始化项目,初始化项目时根据需要选择需要用到的框架(router,vuex),是否需要Eslint验证，选否
vue init webpack my-project

//进入到目录
cd my-project

//安装依赖
npm install

//运行
npm run dev
```

#### vue-cli#2.0 webpack 配置分析
```
|-- build                            // 项目构建(webpack)相关代码
|   |-- build.js                     // 生产环境构建代码
|   |-- check-version.js             // 检查node、npm等版本
|   |-- dev-client.js                // 热重载相关
|   |-- dev-server.js                // 构建本地服务器
|   |-- utils.js                     // 构建工具相关
|   |-- webpack.base.conf.js         // webpack基础配置
|   |-- webpack.dev.conf.js          // webpack开发环境配置
|   |-- webpack.prod.conf.js         // webpack生产环境配置
|-- config                           // 项目开发环境配置
|   |-- dev.env.js                   // 开发环境变量
|   |-- index.js                     // 项目一些配置变量
|   |-- prod.env.js                  // 生产环境变量
|   |-- test.env.js                  // 测试环境变量
|-- src                              // 源码目录
|   |-- components                     // vue公共组件
|   |-- store                          // vuex的状态管理
|   |-- App.vue                        // 页面入口文件
|   |-- main.js                        // 程序入口文件，加载各种公共组件
|-- static                           // 静态文件，比如一些图片，json数据等
|   |-- data                           // 群聊分析得到的数据用于数据可视化
|-- .babelrc                         // ES6语法编译配置
|-- .editorconfig                    // 定义代码格式
|-- .gitignore                       // git上传需要忽略的文件格式
|-- README.md                        // 项目说明
|-- favicon.ico 
|-- index.html                       // 入口页面
|-- package.json                     // 项目基本信息
```

#### 插件
日历插件vue-event-calender 
github中文文档:https://github.com/GeoffZhu/vue-event-calendar/blob/master/README.zh.md
演示地址:http://geoffzhu.cn/vue-event-calendar/