<template>
  <div id="app">
    <v-app>
      <v-content>
        <v-container>
          <swapui msg="A long time ago..."/>
        </v-container>
      </v-content>
    </v-app>
  </div>
</template>

<script>
  import Swapui from './components/Swapui.vue'

  export default {
    name: 'app',
    components: {
      Swapui
    }
  }
</script>

<style>
</style>
