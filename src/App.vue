<template>
  <v-app>
    <v-navigation-drawer absolute persistent :mini-variant.sync="mini"
                         v-model="sideNav" overflow >
      <v-toolbar class="blue darken-3" dark>
        <v-list class="pa-0 blue darken-2" dark>
          <v-list-tile avatar tag="div">
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/16.jpg" />
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title>Marouane Bouhouch</v-list-tile-title>
            </v-list-tile-content>
            <v-list-tile-action>
              <v-btn icon @click.native.stop="mini = !mini">
                <v-icon>chevron_left</v-icon>
              </v-btn>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
      </v-toolbar>
      <v-list class="pt-0" dense>
        <v-divider></v-divider>
        <v-list-tile v-for="item in items" :key="item.title" router :to="item.link">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar class="blue darken-3" dark>
      <v-toolbar-side-icon @click.native.stop="sideNav = !sideNav" class="hidden-sm-and-up"></v-toolbar-side-icon>
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">
          DevMeetups
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only" >
        <v-btn flat  v-for="item in items" :key="item.title">
          <v-icon left>{{ item.icon }}</v-icon >
           {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
      <router-view></router-view>
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        sideNav: false,
        items: [
          { title: 'View Meetups', icon: 'remove_red_eye', link: '/meetups' },
          { title: 'Organize Meetup', icon: 'today', link: '/meetup/new' },
          { title: 'Profile', icon: 'account_circle', link: '/user/profie' },
          { title: 'Sign up', icon: 'supervisor_account', link: '/user/signup' },
          { title: 'Sign in', icon: 'lock_open', link: '/user/signin' }
        ],
        mini: false,
        right: null
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main';
</style>
