<template>
  <v-app light>
    <v-navigation-drawer
      app
      temporary
      v-model="drawer"
      light
      right
    >
      <v-flex text-xs-center class="pl-5">
        <v-list>
          <v-list-tile nuxt :to="item.html" v-for="item in mobileMenuItems" :key="item.title">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-flex>
    </v-navigation-drawer>

    <v-toolbar fixed class="white elevation-1" app>
      <v-spacer></v-spacer>
      <v-btn icon light @click.stop.native="drawer = true" class="">
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>

    <main>
      <v-content fluid>
        <v-container fluid>
          <nuxt />
        </v-container>
      </v-content>
    </main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      mobileMenuItems: [
        {title: 'Home', icon: 'home', html: '/'}
      ]
    }
  }
}
</script>

<style>

</style>
