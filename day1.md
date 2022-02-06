1: vue-cli 脚手架初始化项目
    node + webpack + taobao镜像
    `vue create app`

    node modules文件夹: 项目依赖文件夹

    public文件夹: 放置静态资源(图片), 需要注意, 放在public文件夹中的静态资源, webpack进行打包的时候, 会原封不动打包到dist文件夹中

    src文件夹: 程序员源代码文件夹
        assets文件夹: 放置静态资源(一般放置多个组件共用的静态资源), 需要注意, 放置在assets文件夹中的静态资源, webpack打包的时候, webpack会把静态文件当作一个模块, 打包到JS文件夹里
        
        components文件夹: 一般放置的是非路由组件(全局组件)

        APP.vue: 唯一的根组件, Vue当中的组件(.vue)

        main.js: 程序的入口文件, 也是程序最先执行的文件
    
    babel.config.js: 配置文件(babel相关)

    package.json: 记录项目叫什么, 有哪些依赖, 怎么运行, 项目的 `身份证`

    package-lock.json: 缓存性文件

    README.md: 说明性文件


2: 项目的其它配置
    2.1 项目运行起来的时候, 让浏览器自动打开
    --package.json

    2.2 eslint校验功能关闭
    --在根目录下, 创建一个vue.config.js 配置文件
        比如声明了变量但是没有使用eslint校验工具报错.

    2.3 src文件夹简写方法, 配置别名 @
    {
    "compilerOptions": {
        "baseUrl": "./",
        "paths": {
            "@/*": [
                "src/*"
            ]
        }
    },
    "exclude": [
        "node_modules",
        "dist"
    ]
    }

3: 项目路由的分析
    vue-router
    前端所谓路由: KV键值对.
    key: URL(地址栏中的路径)
    value: 相应的路由组件
    注意: 项目 上中下 结构

    路由组件:
        Home首页路由组件、Search路由组件、login登录路由
    非路由组件:
        Header [首页、搜索页]
        Footer [首页、搜索页], 在登录页没有


4: 完成非路由组件Header与Footer业务
    4.1: 书写静态页面(HTML+CSS)  -- 直接使用老师的
    4.2: 拆分组件
    4.3: 获取服务器的数据动态展示
    4.4: 完成相应的动态业务逻辑

    注意1: 创建组件的时候, 组件结构 + 组件样式 + 图片资源

    注意2: 识别less样式
        npm install --save less less-loader@5
        <style scoped lang="less">
    
    注意3: 使用组件的步骤(非路由组件)
    - 创建或者定义
    - 引入
    - 注册
    - 使用