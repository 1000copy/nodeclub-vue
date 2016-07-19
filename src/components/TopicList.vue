<template>
  <div class="jumbotron">
     <div id="topic_list">
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
      </div>    
  </div>
</template>
<style type="text/css" scoped>
</style>
<script>
  export default {
    data () {
      return {
        items: [
          {message: 'msg1'},
          {message: 'msg2'}]
      }
    }
  }
</script>