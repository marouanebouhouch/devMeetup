<template>
  <v-container>
    <v-layout row wrap class="mb-2">
      <v-flex xs12 sm6 class="text-sm-right text-xs-center">
        <v-btn large router to="/meetup/new" class="blue darken-3" dark>Organize a meetup</v-btn>
      </v-flex>
      <v-flex xs12 sm6 class="text-sm-left text-xs-center" >
        <v-btn large router to="/meetups" class="blue darken-3" dark>Meetups</v-btn>
      </v-flex>
    </v-layout>
    <v-layout row wrap>
        <v-carousel dark>
          <v-carousel-item v-for="(image,i) in images" :src="image.src" :key="i">
            <div class="title">{{ image.title }}</div>
          </v-carousel-item>
        </v-carousel>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        images: [
          {
            src: 'http://www.nationalgeographic.com/content/dam/travel/rights-exempt/Travel-2016/where-the-locals-go/casablanca/city-evening-casablanca-morocco.jpg',
            title: 'Meetup in Casablanca'
          },
          {
            src: 'https://media.timeout.com/images/103042848/image.jpg',
            title: 'Meetup in London'
          },
          {
            src: 'http://www.telegraph.co.uk/content/dam/Travel/Destinations/Europe/France/Paris/paris-attractions-xlarge.jpg',
            title: 'Meetup in Paris'
          },
          {
            src: 'https://media.timeout.com/images/103444978/image.jpg',
            title: 'Meetup in NYC'
          }
        ]
      }
    }
  }
</script>

<style scoped>
  .title{
    position: absolute;
    bottom:50px;
    background-color: rgba(0,0,0,0.5);
    color: white;
    padding: 5px 30px 5px 30px;
  }
</style>
