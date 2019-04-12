<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span><br>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        class="mr-2"
        to="/">
        Home
      </v-btn>
      <v-btn
        class="mr-2"
        to="/about">
        About
      </v-btn>
      <v-btn
        class="mr-2"
        to="/contact">
        Contact
      </v-btn>
      <v-btn
      class="mr-2"
      to="/members">
      Members
    </v-btn>
      <v-btn
        v-on:click="logout"
        class="mr-2"
      v-if="this.$store.state.userIsAthorized">
        Logout
      </v-btn>

    </v-toolbar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      clientId: process.env.VUE_APP_AUTH_CLIENT_ID,
    };
  },
  methods: {
    logout: () => {
      console.log('logging out!')
    },
  },
};
</script>
