<template>
  <div class="container">
    <p>Final Page</p>
    <ul>
      <li><NuxtLink to="/nuxtChild/">Go to /home</NuxtLink></li>
      <li><NuxtLink to="/nuxtChild/parent">Go to /index</NuxtLink></li>
      <li><NuxtLink to="/nuxtChild/parent/child">Go to /child</NuxtLink></li>
      <li><NuxtLink to="/nuxtChild/parent/child2">Go to /child2</NuxtLink></li>
    </ul>
       <hr>
    <div class="box">
        <p>嵌套子页面内容区</p>
        <!-- <nuxt-child>标签在父页面组件中相当于是子页面组件的占位符；嵌套中这个不可少 -->
        <nuxt-child keep-alive :foobar="123"></nuxt-child>
    </div>
  </div>
</template>
