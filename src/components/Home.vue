<template>
 <nav class="container" id="content">
    <section class="row">
      <section class="col-md-9">
        <topic-list class="col-md-12"></topic-list>
      </section>    
      <section class="col-md-3">
        <section class="row">
          <profile></profile>
          <topic-create></topic-create>
          <zero-response></zero-response>
          <score></score>
        </section>
      </section>
    </section>
  </nav>
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

