<template>
	<div class="panel">
	  <div class="header">
	    <span class="col_fade">无人回复的话题</span>
	  </div>
	  <div class="inner">
			<ul class="unstyled">
			  <li v-for="item in items">
			    <div>
			    	<a class="dark topic_title" href="/topic/578da6e5b78759e813a57a41">
			    		{{item.message}}
			    	</a>
			    </div>
			  </li>
			</ul>

	    </div>
	  </div>
	</div>

</template>
<style type="text/css" scoped>
.panel {
    padding: 0px;
    border: 0px;
}</style>

<script>
  export default {
    data () {
      return {
        items: [
        {message: '中国最牛逼的程序员正在编写新的Node.js club！'},
        {message: 'msg2'}
        ]
      }
    }
  }
</script>