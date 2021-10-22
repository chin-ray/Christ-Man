# gofrontend

#### 介绍
vue3.0 + vite + node 全栈开发项目


#### 软件架构
使用 vite 搭建项目，基于 vue3.0 ，后台基于 node.js


#### 安装教程

```
yarn install/npm install
```


#### 使用说明

1. node 中间件运行(/server)

node 中间件多个子项目只需启动一个即可，无需每个子项目都启动 node 中间件

```
// 新起终端执行命令
cd server

// 安装依赖
npm install
// 若报错执行以下命令
npm i http-errors --save -g

npm start
```

2. web 运行(/web)

```
// 切换到前端开发项目
cd web

// 安装依赖
yarn/npm install

yarn dev/npm run dev
```


#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### git 代码提交规范

- feat 增加新功能
- fix 修复问题/BUG
- style 代码风格相关无影响运行结果的
- perf 优化/性能提升
- refactor 重构
- revert 撤销修改
- test 测试相关
- docs 文档/注释
- chore 依赖更新/脚手架配置修改等
- workflow 工作流改进
- ci 持续集成
- types 类型定义文件更改
- wip 开发中


#### 已完成功能



#### 正在开发功能



#### 打包发布
本项目有 node(即 server)承担 web 服务角色（类似 nginx)，所以只需要打包 web 端即可：

- /web 目录下运行命令 `npm run build` 打包 web(打包完成后输出的文件在 dist 文件夹下)
- 将 dist 文件夹下除了 index.html 文件外的其他文件 copy 到 server 目录下 public 文件夹下
- 将 dist 文件夹下的 index.html 文件 copy 到 server 目录下的 views 文件夹下覆盖 index.html
- 将 server 文件夹下非[ node-modules ]文件 copy 到目标服务器上再执行`npm i`安装依赖，运行`npm run start `即可启动访问(使用 pm2 作为 node 的进程管理工具，查看 node 的运行状态及日志等)
