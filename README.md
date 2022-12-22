# Vite启动
```shell
cd vue3-front
npm run dev
```

# Vite目录
## public 该目录中的内容不会被编译，可以存放静态资源。
## src 存放vue源码
### assets 该目录中的内容会被编译，存放需要编译的静态资源。
### components 存放组件
### App.vue是全局入口文件
### main.ts全局的ts配置文件
### vite-env.d.ts 声明扩充
因为默认ts无法识别.vue文件，所以vite通过该文件里的declare module来做声明的扩充，以兼容vue文件。一般不需要修改。
## index.html 
<font color="red">非常重要的入口文件 （webpack，rollup 他们的入口文件都是enrty input 是一个js文件 而Vite 的入口文件是一个html文件，他刚开始不会编译这些js文件 只有当你用到的时候 如script src="xxxxx.js" 会发起一个请求被vite拦截这时候才会解析js文件）</font>
## vite.config.ts是vite的配置文件

# SFC 语法规范
*.vue 件都由三种类型的顶层语法块所组成：&lt;template&gt;、&lt;script&gt;、&lt;style&gt;

## &lt;template&gt;
每个 *.vue 文件最多可同时包含一个顶层 &lt;template&gt; 块。

其中的内容会被提取出来并传递给 @vue/compiler-dom，预编译为 JavaScript 的渲染函数，并附属到导出的组件上作为其 render 选项。

## &lt;script&gt;
每一个 *.vue 文件可以有多个&lt;script&gt;块 (不包括&lt;script setup&gt;)。

该脚本将作为 ES Module 来执行。

其默认导出的内容应该是 Vue 组件选项对象，它要么是一个普通的对象，要么是 defineComponent 的返回值。

&lt;script setup&gt;
每个 *.vue 文件最多只能有一个 &lt;script setup&gt; 块 (不包括常规的 &lt;script&gt;)

该脚本会被预处理并作为组件的 setup() 函数使用，也就是说它会在每个组件实例中执行。&lt;script setup&gt; 的顶层绑定会自动暴露给模板。更多详情请查看 &lt;script setup&gt; 文档。

## &lt;style>
一个 *.vue 文件可以包含多个 &lt;style&gt; 标签。

&lt;style&gt; 标签可以通过 scoped 或 module attribute (更多详情请查看 SFC 样式特性) 将样式封装在当前组件内。多个不同封装模式的 &lt;style&gt; 标签可以在同一个组件中混


[学习Vue3 第四章（模板语法 & vue指令）](https://xiaoman.blog.csdn.net/article/details/122773486?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-122773486-blog-122771007.pc_relevant_3mothn_strategy_and_data_recovery&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-122773486-blog-122771007.pc_relevant_3mothn_strategy_and_data_recovery&utm_relevant_index=1s)