<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2>because we are {{date}}</h2>
    </div>
</template>
<script>
  export default {
    name: 'Swapui',
    props: ['msg'],
    data () {
      return {
        date: new Date()
      }
    }
  }
</script>
<style scoped>

</style>