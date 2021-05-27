<template>
  <v-app>
    <!-- <v-navigation-drawer app> -->
    <!-- </v-navigation-drawer> -->

    <v-app-bar app>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-app-bar-title>Rick & Morty</v-app-bar-title>
      <v-tabs right class="ml-n9" color="green accent-2">
        <v-tab v-for="(link, i) in links" :key="i" :to="link.to">{{
          link.title
        }}</v-tab>
      </v-tabs>
      <!-- -->
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          title: 'Home',
          to: '/home',
        },
        {
          title: 'About',
          to: '/home',
        },
        {
          title: 'Search',
          to: '/home',
        },
      ],
    }
  },
}
</script>
