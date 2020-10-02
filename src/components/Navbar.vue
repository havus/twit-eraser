<template>
  <div>
    <v-app-bar color="#4580E6" flat dense dark>
      <v-toolbar-title class="ml-10">Twit Eraser</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    leftMenus: [
      {
        route: '/',
        text: 'Home',
        icon: 'home',
      },
      {
        route: '/popular',
        text: 'Popular Tag',
        icon: 'star',
      },
    ],
    isLogin: false,
  }),
  methods: {
    logout() {},
  },
  watch: {
    $route() {
      if (localStorage.getItem('token')) {
        this.isLogin = true;
      } else {
        this.isLogin = false;
      }
    },
  },
};
</script>

<style>
  .v-avatar:hover {
    cursor: pointer;
  }
</style>
