[译] Lerna

原文地址： https://lerna.js.org
翻译： shiftj

关于

将大的代码库拆分相互分离的具有独立版本的包，对代码得分享十分有利。然而，这使得跨多仓库的改动是比较杂乱且很难追踪，同时跨仓库测试很快就会变得很复杂。

为了解决这些问题（其实还有很多其他问题），一些项目会将他们的代码库放到一个多个包的仓库中。比如这些项目：Babel，React, Angular, Ember, Meteor, Jest；同时还有很多别的项目用一个代码库开发他们所有的包。

Lerna是一个能优化工作流的工具，围绕管理多包的仓库通过用git和npm。


快速上手

通过npm来全局安装lerna：

Lerna 2.x 是推荐用来上手的版本。

`$ npm install —global lerna`

接下来我们插件一个git仓库：

`$ git init lerna-repo && cd lerna-repo`

让我们将它变成一个lerna 仓库：

`$ lerna init`

你的仓库的目录结构如下：

```
lerna-repo/
    package/
    package.json
    lerna.json
```

命令

下面是对每个命令的简单介绍。访问 README 来获取更详细的信息。

```
lerna init

创建一个新的lerna 仓库 或者 将已存在的仓库的Lerna版本升级。

参数

`—independent` / `-i` - 启用独立版本模式

```

```
lerna bootstarp

在当前Lerna仓库引导包。安装所有依赖并且link所有的交叉依赖。

这个命令是至关重要的，它允许你在`require()`中是使用你的包的名称，就好比这些包已经存在并且已经存在在`node_modules`目录一样。

```

```
lerna import <pathToRepo>


引入本地路径<pathToRepo>下的这个包到 packages/<directory-name>，会产生commit history。
```

```
lerna publish

在一个包已经被更新后，创建一次新的发布。指定一个新版本，并且在git和npm上更新所有的包。

参数

`—npm-tag [tagname]` - 使用给定的npm的dist-tag发布npm

`—canary` / `-c` - 创建一个canary版的发布

`—skip-git` - 跳过所有git操作

`—force-publish [packages]` - 对给定的包（多个包以逗号分隔）执行强制发布，或使用`*`来指定所有包；跳过变化包的git diff检查。
```

```
lerna changed

检查那些包自上次发布以后发生了变动
```

```
lerna diff [package?]

查看所有包或指定包自上次发布以后发生变动的差异点
```

```
lerna run [srcipt]

执行包含指定命令的的每个包内的这条npm script。
```

```
lerna ls

列出当前Lerna仓库的所有公共包。
```


谁在用 Lerna？

* primer/primer
* babel/babel
* facebook/create-react-app
* ReactTraining/react-router
* pugjs/pug
* facebook/jest
* reactotron/reactotron
* ElemeFE/mint-ui
* devtools-html/debugger.html
* alibaba/rax
* Turfjs/turf
* babel/babili
* storybooks/storybook
* xmppjs/xmpp.js
* wooorm/retext
* jumpsuit/jumpsuit
* strapi/strapi
* cloudflare/cf-ui
* colmena/colmena
* angus-c/just
* cerebral/cerebral
* nteract/nteract
* wooorm/remark
* rofrischmann/fela
* tbranyen/diffhtml
* ElemeFE/cooking
* antwarjs/antwar
* apollostack/graphql-server
* jimpick/lambda-comments
* lystable/recon
* marudor/flowInterfaces
* GoogleChrome/sw-helpers
* webpack-preset/webpack-preset
* vazco/uniforms
* metal/metal.js
* steelbrain/pundle
* neos/neos-ui
* mosjs/mos
* lore/lore
* act-framework/act
* yvele/poosh
* noderaider/gridiron
* superawesomelabs/leo
* tocco/tocco-client
* zalando-incubator/tessellate
* sencha/extjs-reactor
* DigitalRiver/react-atlas
* forivall/tacoscript
* Boxable/box-ui
* flux-capacitor/flux-capacitor
* trepo/trepo-js
* spacedoc/spacedoc
* oknosoft/metadata.js
* uber-web/uber-eslint
* brittanica/brittanica
* openzipkin/zipkin-js
* vudash/vudash
* nteract/commuter
* frintjs/frint
* fyndiq/fyndiq-ui
* azu/immutable-array-prototype
* TrueCar/gluestick
* KELiON/create-cerebro-plugin
* phenomic/phenomic
* sterjakovigor/vqua
* wireapp/wire-web-packages
* klis87/redux-saga-requests
* WordPress/gutenberg
* react-cosmos/react-cosmos
* jsbites/jedifocus-monorepo
* FoalTS/foal
* emotion-js/emotion
* Bamieh/reflow
* transloadit/uppy
* olistic/warriorjs
* gatsbyjs/gatsby
* feathersjs/feathers
* vuejs/vue-cli
* dvajs/dva
* umijs/umi
* SBoudrias/Inquirer.js
* pedronauck/docz
* tasitlabs/tasitsdk
* zeit/next.js
* react-bootstrap-table/react-bootstrap-table2
* webpack/webpack-cli
* reakit/reakit
* webdriverio/webdriverio
* graycoreio/daffodil
* typescript-eslint/typescript-eslint
* stoplightio/prism




