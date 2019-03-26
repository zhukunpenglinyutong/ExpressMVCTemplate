### 介绍  ✈️

> 这是本人 用于快速搭建 API 的 Express 做的一个 模板，目前具有快速搭建API，日志记录，安全防护（SQL注入和XSS）的功能，后期还会不断的完善拓展

> 目前版本 v1.0 beta（2019.3.25）

---
### 安装依赖  ⛑

> npm install

---
### 开发目的  🚲

> 目的目前只有一个，做一个开箱即用的 Node 后端服务器集合，v1.* 版本，主要服务于我自己个人开发，v2.* 将会逐渐过渡为 为中小开发者或者团队提供集成开发库的一个Node框架，提供代码规范和Koa，Egg的重构版本

---
### 文件夹 以及 文件介绍  🦀

- bin
  - www.js 服务器配置（专门启动服务器的文件）
- conf
  - db.js 数据库配置相关信息（包括线上和开发数据库配置）
- db 创建数据库对象
  - mysql.js 创建数据库对象 和 数据库查询方法
- controller 业务逻辑文件
  - index.js 主业务逻辑文件，随着逻辑变多 业务逻辑的文件可以拆分，然后统一导入到 index.js 中
- router 路由文件夹
  - index.js 路由配置文件，随着逻辑变多 路由的文件可以拆分，然后统一导入到 index.js 中
- app.js 启动文件

---
### Node服务器 启动以及测试 🐠

- *启动：* npm run dev
- *测试node服务是否启动正常：* http://localhost:3000/test （ 正常打印出来 {"data":{"msg":"测试：node服务器启动成功"},"error":0} ）

- 到此表示 Node服务器启动成功（但是尚未连接数据库）


### 连接数据库 🌲

> conf/db.js 里面的代码要换成 相应的数据了

---
### 下一步规划 📒

- 开发 v1.1 Alpha（`预计2019.3.31日前完成`）
  - 加强安全防护层（目前主要是依赖第三方库做 XSS 和 防止SQL注入的攻击方式），开发防护层 Express中间件
  - 优化数据库连接部分，使其对频繁查询优化（连接池）
  - 增加 日志日志定时分析功能（系统环境Linux）
  - 开发 Basics 分支，增加对登录功能和其周边的实现，包括 Redis记录，登录验证功能（主分支目前主要应用是：在几分钟内搭建出一套简易系统的API，未来将根据自己水平的提升逐渐完善主分支功能，个人水平目前还处在起步阶段）

---

- 发布 v1.1 beta (`预计2019.4.4日前完成`)
  - 增加单元测试
  - 优化目录结构，使其有开源项目基础的骨架 


---
### 拜求指点  🚄🚄🚄

> 因为后端领域不是我的主要开发方向，但是本人对后端开发和安全处理都有很大的兴趣（其实对编程的各个领域都有兴趣😆），但是奈何年龄不到位，知识不给力，积累太少，所做出来的东西，我自己都满足不了，说真的我并不是不会，而是不知道怎么去往下去整，因为目前从事的是前端，后端领域目前（2019.3.26）只停留在分层阶段和功能拆分服务集成那一块，所以如果有大佬看了本项目，觉得可以指点一下迷雾中的我，那我真的是太兴奋了，拜谢拜谢拜谢

- ☁️微信号：lyglyglyg666666
- 🎈QQ号：270750933
- 📮邮箱：270750933@qq.com

---
### 历史版本  ⚓️

- v1.0 beta (2019.3.25)
  - 服务启动由app.js 拆分为 bin/www.js 和 app.js;
  - 耦合于controller中的数据库连接部分拆分为 conf/db.js 和 db/mysql.js 两层
  - controller层中新增 model/resModel.js 格式化输出层
  - 确定以controller层 用于拿到前台给到的数据，也用于返回给前台数据，router层只用于做路由处理，db/mysql.js 做数据库连接和查询功能
  - 增加 XSS 和 防SQL注入 和 日志功能（3.26日晚上添加）

> 总结就是：将一些功能解耦

---
- v0.91 beta（2019.3.4）

> 具有简单的 MVC 架构，即：路由层，controller层

---


