<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12 sm10 md8 offset-md2 offset-sm1 v-for="meetup in meetups" :key="meetup.id" class="mb-2">
        <v-card>
          <v-card-media
            class="white--text"
            height="200px"
            :src="meetup.src"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                  <span class="headline title">{{ meetup.title }}</span>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
              <span class="grey--text">{{ meetup.date }}</span><br>
          </v-card-title>
          <v-card-actions>
            <v-btn flat class="blue--text">
              <v-icon left blue>remove_red_eye</v-icon>
              View
            </v-btn>
            <v-btn flat class="blue--text">
              <v-icon left blue>arrow_forward</v-icon>
              Register
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
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
            title: 'Meetup in Casablanca',
            date: '12/10/2017 10:30'
          },
          {
            id: 2,
            src: 'https://media.timeout.com/images/103042848/image.jpg',
            title: 'Meetup in London',
            date: '12/10/2017 10:30'
          },
          {
            id: 3,
            src: 'http://www.telegraph.co.uk/content/dam/Travel/Destinations/Europe/France/Paris/paris-attractions-xlarge.jpg',
            title: 'Meetup in Paris',
            date: '12/10/2017 10:30'
          },
          {
            id: 4,
            src: 'https://media.timeout.com/images/103444978/image.jpg',
            title: 'Meetup in NYC',
            date: '12/10/2017 10:30'
          }
        ]
      }
    }
  }
</script>

<style scoped>
  .title{
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: rgba(0,0,0,0.5);
    padding: 8px 30px 8px 30px;
    border-top-right-radius: 10px;
  }
</style>
