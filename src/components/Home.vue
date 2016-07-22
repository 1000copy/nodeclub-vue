<template>
 <div class="container" id="content">
    <div class="row">
      <div class="col-md-9">
        <div class="col-md-12 topic-header">
          <a href="/home/all" class="topic-tab current-tab">全部</a>
          <a href="/home/good" class="topic-tab ">精华</a>
          <a href="/?tab=share" class="topic-tab ">分享</a>
          <a href="/?tab=ask" class="topic-tab ">问答</a>
          <a href="/?tab=job" class="topic-tab ">招聘</a>
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
        console.log('tab:' + this.$route.params.tab)
        transition.next({
          items: [
            {message: '中国最牛逼的程序员正在编写新的Node.js club！'},
            {message: 'msg2'}
          ]
        })
      }
    },
    data () {
      return {}
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

