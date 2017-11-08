<template>
  <v-app light>
    <v-navigation-drawer
      app
      enable-resize-watcher
      disable-route-watcher
      persistent
      v-model="drawer"
      light
      >
      <v-list>
        <v-list-tile v-for="item in menuItems" :key="item.title" :to="item.html">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <main>
      <v-content fluid class="pt-0">
        <v-container fluid style="padding:0px;">
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
      drawer: true,
      snackText: '',
      snackOn: false,
      menuItems: [
        {
          title: 'Temp Right',
          icon: 'bug_report',
          html: '/temporary-right'
        }
      ]
    }
  }
}
</script>

<style>

</style>
