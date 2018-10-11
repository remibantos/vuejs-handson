<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2 :title="dateTitle">because we are {{date}}</h2>
        <div :key="character" v-for="character in characters"><span v-if="character !== 'Boba Fett'">{{character}}</span></div>
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
        dateTitle: 'This is the date',
        characters: ['Boba Fett', 'Leia Skywalker']
      }
    }
  }
</script>
<style scoped>

</style>