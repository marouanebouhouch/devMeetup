<template>
  <v-container>
    <v-layout row wrap class="mb-2">
      <v-flex xs12 sm6 class="text-sm-right text-xs-center" >
        <v-btn large router to="/meetups" class="blue darken-3" dark>View Meetups</v-btn>
      </v-flex>
      <v-flex xs12 sm6 class="text-sm-left text-xs-center">
        <v-btn large router to="/meetup/new" class="blue darken-3" dark>Organize meetup</v-btn>
      </v-flex>
    </v-layout>
    <v-layout row wrap>
        <v-carousel dark>
          <v-carousel-item v-for="meetup in meetups" :src="meetup.src" :key="meetup.id">
            <div class="title">{{ meetup.title }}</div>
          </v-carousel-item>
        </v-carousel>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        meetups: [
          {
            id: 1,
            src: 'http://www.nationalgeographic.com/content/dam/travel/rights-exempt/Travel-2016/where-the-locals-go/casablanca/city-evening-casablanca-morocco.jpg',
            title: 'Meetup in Casablanca'
          },
          {
            id: 2,
            src: 'https://media.timeout.com/images/103042848/image.jpg',
            title: 'Meetup in London'
          },
          {
            id: 3,
            src: 'http://www.telegraph.co.uk/content/dam/Travel/Destinations/Europe/France/Paris/paris-attractions-xlarge.jpg',
            title: 'Meetup in Paris'
          },
          {
            id: 4,
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
