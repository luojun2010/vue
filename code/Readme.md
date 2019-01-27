
# Vue-resource实现get, post jsonp请求
  1. 之前的学习中，如何发起数据请求？
  2. 常见的数据请求类型？ get, post jsonp


# Vue.js   -Day3

## 定义Vue组件
   什么是组：组件的出现，就是为了拆分Vue实例的代码量的，能够让我们以不同的组件，来划分不同的功能 模块，将来
   我们需要什么样的功能，就可以去调用对就的组件即可;

 组件化和模块化的不同：
   +  模块化： 是从代码逻辑的角度进行划分，方便代码分层开发；保证每个功能职能单一;
   +  组件化： 是从UI界面的角度进行划分的;方便UI组件重用；
        
# 全局组件定义的三种方式
  1. 使用 Vue.extend 配合 Vue.component 方法:

  var login = Vue.extend({
    template: '<h1>登录</h1>'
  });
  Vue.component('login', login);

  2. 直接使用 Vue.component 方法
     
     Vue.component('register',{
       template:<h1>注册</h1>
     });

  3. 将模板字符串，定义到script标签种:
    <script id='tmpl' type='x-template'> 
      <div><a href="#">登录</a> <a href="#">注册</a> </div>
    </script>
   
   同时, 需要使用 Vue.component 来定义组件
     
     Vue.component('account',{
       template: '#tmpl'
     });


# Vue.js   -Day4
# 父组件向子组件传值
  1. 组件实例定义方式, 注意: 一定要使用 props 属性来定义父组传递过来的的数据
  <script>
    // 创建 Vue 实例，得到 ViewModel
    var vm = new Vue({{
      el: '#app',
      data:{ msg: '这是父组件的消息' }
    },
    components: {
      son:{
        template： '<h1>这是子组件 --- {{finfo}} </h1>'
        props: ['finfo']
      }
    });
  </script>

  2. 使用 v-bind 或简化指令，将数据传递到子组件中:
   <div id='app'>
     <son : finfo="msg"></son>
   </div>

## 子组件向父组件传值
1. 原理：父组件将方法的引用,传递到子组件内部调用父组件传递过来的方法,同时把要发送给父组件的数据,在调用方法的时候当作参数传递进去;
2. 父组件将方法 的引用传递给子组件,其中， 'getXsg' 是父组件中 'methods' 中定义的方法名称, 'func'是子组件调用传递过来方法时候的方法名称
 

 ## 什么是路由
1. ** 后端路由: **对于普通的网站,所有的超链接都是 URL 地址,所有的 URL 地址都对应服务器上对应的资源;
2. ** 前端路由：**对于单页面应用程序来说, 主要通过URL中的 hash(#号)来实现页面之间的切换,
   同时， hash 有一个特点： HTTP请求中不会包含hash相关的内容; 所以，单页面程序中的页面跳转主要用hash实现
3.  在单页面应用程序中,这种通过hash改变来切页页的方式，称前端路由(区别于后端路由);

## 在 vue 中使用 vue-router


 

