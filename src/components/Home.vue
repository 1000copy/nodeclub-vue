<template>
 <div class="container" id="content">
    <div class="row">
      <div class="col-md-9">
        <div class="col-md-12 topic-header">
          <a v-link="{path:'/home/all'}" class="hometab topic-tab current-tab">全部</a>
          <a v-link="{path:'/home/good'}" class="hometab topic-tab ">精华</a>
          <a v-link="{path:'/home/share'}"class="hometab topic-tab ">分享</a>
        </div>
        <topic-list class="col-md-12"></topic-list>
   
      </div>    
      <div class="col-md-3">
        <div class="row">
          <profile class="col-md-12"></profile>
          <topic-create class="col-md-12"></topic-create>
          <zero-response class="col-md-12"></zero-response>
          <score class="col-md-12"></score>
        </div>
      </div>
    </div>        
  </div>
    <!-- <div class="row"> -->
  <footer class="col-md-12 col-lg-12"></footer>
    <!-- </div> -->
</div>
</template>

<script>
  import Profile from './Profile.vue'
  import TopicCreate from './TopicCreate.vue'
  import TopicList from './TopicList.vue'
  import ZeroResponse from './ZeroResponse.vue'
  import Score from './Score.vue'
  export default {
    components: {
      'profile': Profile,
      'topic-create': TopicCreate,
      'topic-list': TopicList,
      'zero-response': ZeroResponse,
      'score': Score
    },
    route: {
      data: function (transition) {
        var arr = ['all', 'good', 'share']
        var ki = arr.indexOf(this.$route.params.tab)
        var els = document.querySelectorAll('.hometab')
        for (var i = 0; i < els.length; i++) {
          els[i].classList.remove('current-tab')
          if (i === ki) {
            els[i].classList.add('current-tab')
          }
        }
        this.$broadcast('tab-change', this.$route.params.tab)
        transition.next()
      }
    }
  }
</script>

<style type="text/css" scoped>
.topic-header {
    padding: 10px;
    background-color: #f6f6f6;
    border-radius: 3px 3px 0 0;
}
#content{
  margin: 15px auto
}
</style>

