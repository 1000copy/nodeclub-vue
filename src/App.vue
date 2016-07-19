<template>
  <div id="wrapper">
    <div class="navbar">
      <div class="navbar-inner">
        <div class="container">
          <a class="brand" href="/">
              <img src="assets/cnodejs_light.svg">
          </a>

          <form id="search_form" class="navbar-search" action="/search">
            <input type="text" id="q" name="q" class="search-query span3" value="">
          </form>
          <ul class="nav pull-right">
            <li><a href="/">首页</a></li>
            
            <li>
                <a href="/my/messages">
                  
                  未读消息
                </a>
            </li>
            
            <li><a href="/getstart">新手入门</a></li>
            <li><a href="/api">API</a></li>
            
            <li><a href="/about" target="">关于</a></li>
            
            
            <li><a href="/setting">设置</a></li>
            <li>
              <a href="/signout" data-method="post" rel="nofollow">退出</a>
            </li>
            
          </ul>
          <a class="btn btn-navbar" id="responsive-sidebar-trigger">
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </a>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="col-md-12">
        <router-view></router-view>
    </div>
    <div class="container">
        <footer_>
        </footer_>
    </div>
  </div>
</template>

<script>
  import Sidebar from './components/Sidebar.vue'
  import Footer from './components/Footer.vue'
  // import Ad from './components/Ad.vue'
  export default {
    components: {
      'sidebar': Sidebar,
      'footer_': Footer
    },
    data () {
      return {
        // Start with the same value as our
        // first time entry. Hard-coded for now
        // because we'll use a different approach
        // in the next article anyway
        totalTime: 1.5
      }
    },
    events: {
      // Increment the totalTime value based on the new
      // time entry that is dispatched up
      timeUpdate (timeEntry) {
        this.totalTime += parseFloat(timeEntry.totalTime)
      },
      // Decrement totalTime when a time entry is deleted
      deleteTime (timeEntry) {
        this.totalTime -= parseFloat(timeEntry.totalTime)
      }
    }
  }
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}


</style>
