<template>
 
  <div class="navbar">
    <div class="navbar-inner">
      <!-- <div class="container"> -->
        <a class="brand" href="/">
        <img src="assets/cnodejs_light.svg">
        </a>
        <form id="search_form" class="navbar-search" action="/search">
          <input type="text" id="q" name="q" class="search-query" value="">
        </form>
        <ul class="nav pull-right">
          <li><a v-link="{path:'/home'}" class="topic-tab">首页</a></li>
          <li><a v-link="{path:'/about'}" class="topic-tab">关于</a></li>
        </ul>
      <!-- </div> -->
    </div>
  </div>
  <div >
      <router-view></router-view>
  </div>
  <footer_></footer_>  



</template>

<script>
  import Sidebar from './components/Sidebar.vue'
  import Footer from './components/Footer.vue'
  // import Ad from './components/Ad.vue'
  export default {
    components: {
      'sidebar': Sidebar,
      'footer_': Footer
    }
  }
</script>

<style>

/*body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}
*/
#app {
  color: #2c3e50;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.navbar {
    top: 0px;
    width: 100%;
    border-radius: 0px!important;
}
.navbar .brand {
    width: 160px;
    /*padding: 3px 20px;*/
    height: 34px;
}
.navbar-search {
    margin-bottom: 0;
       width: 233px;
    /*padding: 3px 20px;*/
    height: 28px; 
}
form {
    margin: 0 0 20px;
}
#q{
    width: 233px;
    height: 26px;  
}
</style>
