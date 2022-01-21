## 一键静态化
- 使用下面的命令生成应用的静态目录和文件：
```
npm run generate
```
- 可在config.js中配置目录的文件的名字
```
generate:{
  dir: 'my-site'
}
```
## 目录结构
1. 布局目录
  ```
  //layouts/defaut.vue
  1. 默认布局
  <template>
  <div>
    <Header></Header>  // conponents中的组件
    <Nuxt />  //page中的组件
    <Footer></Footer>  //conponents中的组件
  </div> 
  </template>

  2. 自定义布局
  //1、layout/blog.vue
  <div>
    <div>My blog navigation bar here</div>
    <Nuxt/>
  </div>
  // 2、pages/index.vue
  <script>
    export default {
      layout: 'blog'
    }
  </script>
  
  ```