### NUXT 版本 1.4.2

## 安装

1. npm install -g @vue/cli-init
2. vue init nuxt-community/koa-template nuxt-koa-learn
3. cd nuxt-koa-learn
4. npm uninstall nuxt
5. npm install nuxt@1.4.2
6. npm i koa-router

## 目录
1. components放组件  
2. layout目录是模板文件  组件中用layout引用对应的模板
3. pages是路由文件 新建即添加路由
4. store 是VUEX文件夹


## 跑KOA服务

1. 新建 `server/interface/city.js`

2. `server/index.js` 中引入 并运行 
`  app.use(cityInterface.routes()).use(cityInterface.allowedMethods())`

3. 新建 gitBash 输入 `curl http://localhost:3000/city/list` 可查询出刚才建的
   也可以在浏览器直接访问


## 服务端渲染

1. search.vue中 传统通过 axios 方法调用刚才的的list接口 查看页面源码 是查不到异步返回的数据的，

2. asyncData方法可以获得异步数据 源码中有异步数据,此方法代替传统的created,mounted里抓异步数据

3. fetch 主要用于处理vuex的数据 可看文档


## VUEX
1. 新建STORE 文件夹

2. vuex 的数据也能正常显示在源码中