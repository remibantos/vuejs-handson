<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2>because we are {{date}}</h2>
    </div>
</template>
<script>

  import moment from 'moment'
  export default {
    name: 'Swapui',
    props: ['msg'],
    data () {
      return {
        date: moment().format('LLLL')
      }
    }
  }
</script>
<style scoped>

</style>