<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.id}`"
        text
        rounded
        :to="link.url"
      >{{ link.label }}</v-btn>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

    <v-footer color="primary lighten-1" padless>
      <v-layout justify-center wrap>
        <v-btn
            v-for="link in links"
            :key="link.id"
            color="white"
            text
            rounded
            class="my-2"
            :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-flex primary lighten-2 py-4 text-center white--text xs12>
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data: () => ({
    links: [
      {
        label: 'Home',
        url: '/',
        id: 1
      },
      {
        label: 'Login',
        url: '/login',
        id: 2
      },
      {
        label: 'Dashboard',
        url: '/dashboard',
        id: 3
      }
    ]
  }),
};
</script>
