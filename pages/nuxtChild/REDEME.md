### 1 .一级路由
- 路由中的nuxt的两个特点：
  - 摒弃了 vue 中的路由表，改为文件结构自动生成的路由，比如 pages/users/index.vue，即生成 /users 对应的路由，当然也可以使用 pages/users.vue 渲染该路由，比较灵活。
  - 将 Vue 中的 Layout 单独抽为 视图 概念，在 nuxt 项目根目录的 layouts 文件夹内编写。
> 抽取 Layout 为单独一个视图概念之后，我们就要把之前在 Vue 中的 Layout 组件内容写在 nuxt 项目根目录下的视图文件夹 layouts 内，把他作为一个视图
- 在文件夹内，nuxt提供了一个视图default.vue:
```javascript
//我们发现，这里的 <Nuxt /> 就是在 Vue 中的第一级路由 <router-view /> 渲染入口。
	<template>
	  <div>
	    <Nuxt />
	  </div>
	</template>
```
### 2. 嵌套路由
在 nuxt 中，多级嵌套路由是 主文件 + 同名文件夹 的模式：

举个例子，
- 在 pages/nuxtChild/parent.vue 会形成 /parent 这个页面，
- 我们再创建一个 pages/nuxtChild/parent/index.vue 就形成了多级路由，在 pages/nuxtChild/parent.vue 内就可以加入：
```javascript
// 进而就会在此处渲染同名文件夹内的子路由(默认渲染pages/nuxtChild/parent/index.vue)
<nuxt-child />
```
<font color="red">注：</font>对于 /users 这个页面，创建 pages/nuxtChild/parent.vue 和 pages/nuxtChild/parent/index.vue 是等价的，而当这两个同时存在时，就形成了嵌套路由的使用模式。
- 嵌套路由只是多了一层同名文件夹而已
### 3. 总结
##### 路由模式
<table>
    <thead>
        <tr>
            <th></th>
            <th>Nuxt</th>
            <th>Vue</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>路由形成模式</td>
            <td>动态生成</td>
            <td>需要配置路由表</td>
        </tr>
    </tbody>
</table>
###### 路由入口写法
<table><thead><tr><th></th><th>Nuxt</th><th>Vue</th></tr></thead><tbody><tr><td>第一级路由</td><td><code>&lt;Nuxt /&gt;</code></td><td><code>&lt;router-view /&gt;</code></td></tr><tr><td>多级嵌套路由</td><td><code>&lt;nuxt-child /&gt;</code></td><td><code>&lt;router-view /&gt;</code></td></tr></tbody></table>
###### 路由入口位置
<table><thead><tr><th></th><th>Nuxt</th><th>Vue</th></tr></thead><tbody><tr><td>第一级路由入口</td><td>单独的 layouts 视图文件夹内的页面中写入口</td><td>一个普通 vue 页面文件中写入口</td></tr><tr><td>多级嵌套路由入口</td><td>主文件 + 同名文件夹模式<br>（入口在主文件内）</td><td>第一级路由入口页面内</td></tr></tbody></table>
<p>在 nuxt 中， <code>pages</code> 中的每个页面需要使用什么布局，在 <code>layout</code> 函数或字符串上指定即可，详见 nuxt.js <a href="https://zh.nuxtjs.org/api/pages-layout">使用说明</a>。</p>


