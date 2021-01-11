<template>
  <v-app>
    <navigation/>
    <v-main class="grey lighten-4">
      <v-container fluid>
        <router-view></router-view>
      </v-container>
  </v-main>
  </v-app>
</template>

<script>
import Navigation from './components/NavigationComponent';

export default {
  name: 'App',

  components: {
    Navigation,
  },

  data: () => ({
    //
  }),
};
</script>
