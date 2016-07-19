<template>
 <div class="container" id="content">
    <div class="row">
      <div class="col-md-8">
        <div class="col-md-12 topic-header">
          <a href="/?tab=all" class="topic-tab current-tab">全部</a>
          <a href="/?tab=good" class="topic-tab ">精华</a>
          <a href="/?tab=share" class="topic-tab ">分享</a>
          <a href="/?tab=ask" class="topic-tab ">问答</a>
          <a href="/?tab=job" class="topic-tab ">招聘</a>
        </div>
        <topic-list class="col-md-12"></topic-list>
        <div class="pagination" current_page="1" class="col-md-12">
          <ul>
            <li class="disabled"><a>«</a></li>
            <li class="disabled active"><a>1</a></li>
            <li><a href="/?tab=all&amp;page=2">2</a></li>
            <li><a href="/?tab=all&amp;page=3">3</a></li>
            <li><a href="/?tab=all&amp;page=4">4</a></li>
            <li><a href="/?tab=all&amp;page=5">5</a></li>
            <li><a>...</a></li>
            <li><a href="/?tab=all&amp;page=455">»</a></li>
          </ul>
        </div>
      </div>    
      <div class="col-md-4">
        <div class="row">
          <profile class="col-md-12"></profile>
          <ad class="col-md-12"></ad>
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
  import Ad from './Ad.vue'
  import TopicList from './TopicList.vue'
  export default {
    components: {
      'profile': Profile,
      'ad': Ad,
      'topic-list': TopicList
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

