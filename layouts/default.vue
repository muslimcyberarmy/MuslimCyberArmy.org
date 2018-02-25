<template>
  <v-app light>
    <v-navigation-drawer
      :mini-variant="true"
      fixed
      app
      dark
      disable-route-watcher
      v-model="drawer"
      class="grey darken-4"
    >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed app class="blue accent-4 white--text elevation-0">
      <v-toolbar-side-icon @click="drawer = !drawer" class="white--text"></v-toolbar-side-icon>
      <input type="text" placeholder="Search" class="mca-input">
      <v-spacer></v-spacer>
      <v-btn
        icon
      >
        <v-icon class="white--text">apps</v-icon>
      </v-btn>
      <!--<v-toolbar-title v-text="title"></v-toolbar-title>-->
    </v-toolbar>
    <v-content>
      <v-container fluid class="pa-0">
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span class="f-normal">&copy; 2018</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: true,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Welcome', to: '/' },
          { icon: 'trending_up', title: 'Trends', to: '/s' },
          { icon: 'lightbulb_outline', title: 'Dakwah', to: '/ss' }
        ],
        title: 'MuslimCyberArmy.org'
      }
    }
  }
</script>
