<template>
 <div class="container">
   <div class="row">
      <div class="col-lg-8">
        <h1>Home</h1>
        <p>
          <strong>
            Get started by <a v-link="'/time-entries'">creating a time entry</a>.
          </strong>
        </p>  
      </div>    
      <div class="col-lg-4">
        <div class="row">
          <profile class="col-lg-12"></profile>
          <ad class="col-lg-12"></ad>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Profile from './Profile.vue'
  import Ad from './Ad.vue'
  export default {
    components: {
      'profile': Profile,
      'ad': Ad
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

<style type="text/css" scoped>
h1{
	/*background: url('../assets/logo.png');*/
}
</style>

