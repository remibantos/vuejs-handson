<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2 :title="dateTitle">because we are {{date}}</h2>
        <v-layout>
            <v-flex :key="character" v-for="character in characters">
                <v-card>
                    <v-card-title>
                        <span>{{character.name}}</span>
                    </v-card-title>
                    <v-img height="350px" :src="character.src"></v-img>
                </v-card>
            </v-flex>
        </v-layout>
    </div>
</template>
<script>

  import moment from 'moment'

  export default {
    name: 'Swapui',
    props: ['msg'],
    data() {
      return {
        date: moment().format('LLLL'),
        dateTitle: 'This is the date',
        characters: [
          {
            name: 'Boba Fett',
            src: 'http://fr.web.img3.acsta.net/r_1920_1080/newsv7/18/05/25/07/43/26079630.jpg'
          },
          {
            name: 'Jabba the Hutt',
            src: 'http://fr.web.img5.acsta.net/r_1920_1080/newsv7/18/05/25/07/43/42131530.png'
          },
          {
            name: 'Han Solo',
            src: 'https://photos.lci.fr/images/613/344/han-solo-star-wars-1b8f56-1@1x.jpeg'
          },]
      }
    }
  }
</script>
<style scoped>

</style>