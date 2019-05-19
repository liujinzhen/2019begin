## 路由


### 基本写法
 	<!-- 使用 router-link 组件来导航. -->
      <!-- 通过传入 `to` 属性指定链接. -->
      <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->

      <router-link to="/home">首页</router-link>
      <router-link to="/news/zz">郑州新闻</router-link>
      <router-link to="/news/bj">北京新闻</router-link>
      <router-link to="/about">关于</router-link


	<!-- 路由出口 -->
    <!-- 路由匹配到的组件将渲染在这里 -->
    <router-view></router-view>


### 步骤

1. 执行use  把VueRouter挂载到Vue对象上
 	
	- Vue.use(VueRouter)
+ 需要两个组件
    - const Home = {template:'<div></div>'};
    - const News = {template:'<div></div>'};

+ 构建vueRouter的实例对象
    - const router = new VueRouter({
        routes: [
          { path: '/home', component: Home },
          { path: '/news/:id',component: News,}
+  把router加载到当前的vue实例对象
      var vm = new Vue({
        el: '#app',
        router,} //这里的router:router 简写为router

### 路由传参
+  { path: '/user/:id', component: User }
+ 参数获取  $route.params.xx

### 嵌套路由
+ 哪个页面需要嵌套 在哪个页面添加<router-view>

### 编程式导航
+ push
+ replace
+ go

### 命名路由

### 添加高亮

