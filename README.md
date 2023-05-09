# 使用说明

自动引入的目录：

- `components/`：存放 vue 组件
- `composables/`：存放 vue 组合函数
- `utils/`：存放一些工具函数

> 也可以使用 `#imports` 别名进行显示引入

约定式路由：在 pages/ 目录内的文件被视作路由页面，路径就是路由地址。

## Rendering Modes

- CSR：客户端渲染
  - 优点：开发速度快，更低的成本，支持离线
  - 缺点：客户端性能开销，SEO 效果不好
    > 适合 SaaS，后台应用程序或在线游戏。交互多，无需 SEO，用户量小，无需频繁访问。
- UR：通用渲染 -> 浏览器请求一个 URL 时，服务器会返回一个完整的渲染完成的页面给客户端，无论页面是提前生成缓存还是动态渲染，Nuxt 都会在服务器环境运行 js，渲染 vue 代码生成 html。
  使得静态页面在浏览器上具有交互性的概念叫做 Hydration。
  - 优点：性能好，用户可以立即访问页面上的内容而无需等待，同时在 Hydration 过程中保持界面的可交互性；SEO 效果好。
  - 缺点：要区分客户端和服务端两套 API，开发成本高；服务器性能要好，运行成本高。
- [HR](https://nuxt.com/docs/guide/concepts/rendering#route-rules)：Hybrid Rendering -> 针对不同路由，可以选择不同的渲染方式，比如首页使用 UR，其他页面使用 CSR
- Rendering on CDN Edge Workers：传统的 SSR 和 UR 仅支持在服务器上渲染，nuxt3 则支持在 CDN 上渲染，减少延迟和服务器成本。（底层由 Nitro 支持）
