<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2 :title="dateTitle">because we are {{date}}</h2>
    </div>
</template>
<script>

  import moment from 'moment'
  export default {
    name: 'Swapui',
    props: ['msg'],
    data () {
      return {
        date: moment().format('LLLL'),
        dateTitle: 'This is the date'
      }
    }
  }
</script>
<style scoped>

</style>