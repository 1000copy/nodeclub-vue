<template>
   <div id="topic-list">
      <div class="cell" v-for="item in items">
        <a class="user_avatar pull-left" href="/user/xeodou">
        <img src="//gravatar.com/avatar/dbefd0e4d332a8d252c0251075262e8d?s=48" title="xeodou">
        </a>
        <span class="reply_count pull-left">
        <span class="count_of_replies" title="回复数">
        38
        </span>
        <span class="count_seperator">/</span>
        <span class="count_of_visits" title="点击数">
        8581
        </span>
        </span>
        <a class="last_time pull-right" href="/topic/575e70ef4a43c1cb159ffe25#578350ba69d72f545483cac5">
        <img class="user_small_avatar" src="https://avatars.githubusercontent.com/u/8020726?v=3&amp;s=120">
        <span class="last_active_time">8 天前</span>
        </a>
        <div class="topic_title_wrapper">
          <span class="put_top">置顶</span>
          <a class="topic_title" href="/topic/575e70ef4a43c1cb159ffe25" title="{{item.message}}">
          {{item.message}}
          </a>
        </div>
      </div>
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
</template>
<style type="text/css" scoped>
#topic-list{
  background: #fff;
  padding-right: 0px;
  padding-left: 0px;
}
#topic-list .cell {
    padding-right: 10px;
    background: #fff;
    border-top: 1px solid #f0f0f0;
    padding: 10px 0 10px 10px;
}
#topic-list .cell:nth-child(1) {
    border-top: none;
}
</style>
<script>
  export default {
    props: ['tab'],
    data () {
      console.log('topiclist tab:' + this.tab)
      return {
        items: [
            {message: '中国最牛逼的程序员正在编写新的Node.js club！'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'},
            {message: 'msg2'}
        ]}
    },
    route: {
      // activate: function (transition) {
      //   console.log('hook-example activated!')
      //   transition.next()
      // },
      // deactivate: function (transition) {
      //   console.log('hook-example deactivated!')
      //   transition.next()
      // }
    },
    watch: {
      tab: function (value) {
        if (value === 'good') {
          this.$set('items', [{message: 'good'}, {message: 'msg2'}])
        } else {
          this.$set('items', [{message: 'all'}, {message: 'msg2'}])
        }
      }
    },
    // data: function (transition) {
    //   console.log('hook-example data!')
    //   transition.next()
    // },
    canReuse: function (transition) {
      console.log('topiclist tab:' + this.tab)
      return false
    }
  }
</script>