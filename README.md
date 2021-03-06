# wx-promise-pro

强大的、优雅的 小程序 Promise 库，wx-promise-pro 不仅仅把微信小程序所有异步 API promise 化，还把许多优雅的解决方案封装成方法挂载到 `wx.pro` 对象下。所以在 wx-promise-pro 中，pro 既有 promise 的含义又有扩展的意思。

[![Financial Contributors on Open Collective](https://opencollective.com/wx-promise-pro/all/badge.svg?label=financial+contributors)](https://opencollective.com/wx-promise-pro) [![npm](https://img.shields.io/npm/v/wx-promise-pro.svg)](https://www.npmjs.com/package/wx-promise-pro) [![npm](https://img.shields.io/npm/dm/wx-promise-pro.svg)](https://www.npmjs.com/package/wx-promise-pro)

[![NPM](https://nodei.co/npm/wx-promise-pro.png?compact=true)](https://nodei.co/npm/wx-promise-pro/)

## 使用

### 普通使用方法

将 `wxPromise.min.js` copy 到 utils 目录中，然后在 `app.js` 中引入： `import './utils/wxPromise.min.js'`。

本库分为两个部分，一部分是将微信小程序原有的API promise 化，一部分是我自己封装的常用方法。两部分的方法都是挂载在 `wx.pro` 对象下，使用的时候直接使用 `wx.pro` 对象调用即可。

如果想要支持 async 和 await，请仔细阅读 **支持 async和await** 这一节。

### 使用NPM

如果你在小程序项目中使用的 NPM 来作为包管理器，或者你使用 mpvue 开发小程序，那么可以直接使用 npm 来安装 `wx-promise-pro`

```bash
npm i wx-promise-pro
```

然后使用 nodejs（`require('wx-promise-pro')`）或者 ES6 Moudle（`import 'wx-promise-pro'`） 的方式引入。

### 支持 async、await

> 由于 wx-promise-pro 是直接内置了 regenerator-runtime，所以推荐使用压缩版，体积不到10k

页面引入 regeneratorRuntime: `import regeneratorRuntime from '/utils/wxPromise.min.js'`

> 注意：导入 regeneratorRuntime 和原本 `wx.pro` 对象是不冲突的，你如果用不到 async 函数，那么可以不导入 regeneratorRuntime

[点击](./detail/async.md) 查看关于 async 的 demo，或者 [点击](http://es6.ruanyifeng.com/#docs/async) 学习 async 的语法。

## 支持所有的微信小程序异步API

使用 wxPromise 开发者无需关心兼容与否，只要是 `wx` 支持的 api，`wx.pro` 全部支持。

**示例代码：**

```js
// 演示 wxPromise 的能力
wx.pro.showLoading({
  title: '加载中',
  mask: true
})
wx.pro.request({
  url: 'https://cnodejs.org/api/v1/topics',
  data: {},
  method: 'GET',
  header: {'content-type': 'application/json'}
}).then(res => {
  console.log(res)
}).catch(err => {
  console.log(err)
}).finally(() => {
  wx.hideLoading()
})
```

## Contributors

### Code Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].
<a href="https://github.com/youngjuning/wx-promise-pro/graphs/contributors"><img src="https://opencollective.com/wx-promise-pro/contributors.svg?width=890&button=false" /></a>

### Financial Contributors

Become a financial contributor and help us sustain our community. [[Contribute](https://opencollective.com/wx-promise-pro/contribute)]

#### Individuals

<a href="https://opencollective.com/wx-promise-pro"><img src="https://opencollective.com/wx-promise-pro/individuals.svg?width=890"></a>

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. [[Contribute](https://opencollective.com/wx-promise-pro/contribute)]

<a href="https://opencollective.com/wx-promise-pro/organization/0/website"><img src="https://opencollective.com/wx-promise-pro/organization/0/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/1/website"><img src="https://opencollective.com/wx-promise-pro/organization/1/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/2/website"><img src="https://opencollective.com/wx-promise-pro/organization/2/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/3/website"><img src="https://opencollective.com/wx-promise-pro/organization/3/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/4/website"><img src="https://opencollective.com/wx-promise-pro/organization/4/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/5/website"><img src="https://opencollective.com/wx-promise-pro/organization/5/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/6/website"><img src="https://opencollective.com/wx-promise-pro/organization/6/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/7/website"><img src="https://opencollective.com/wx-promise-pro/organization/7/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/8/website"><img src="https://opencollective.com/wx-promise-pro/organization/8/avatar.svg"></a>
<a href="https://opencollective.com/wx-promise-pro/organization/9/website"><img src="https://opencollective.com/wx-promise-pro/organization/9/avatar.svg"></a>
