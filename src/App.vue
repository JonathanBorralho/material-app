<template>
  <v-app>

    <v-navigation-drawer
      app
      v-model="drawer"
      :clipped="true"
    >
      <NavigationMenu :items="items"></NavigationMenu>

    </v-navigation-drawer>

    <v-app-bar
      app
      color="blue darken-3"
      dark
      :clipped-left="true"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" />

      <v-toolbar-title>Empreendimentos</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-logout</v-icon>
          </v-btn>
        </template>
        <span>Logout</span>
      </v-tooltip>
    </v-app-bar>

    <v-content>
      <div>Teste</div>
    </v-content>

    <v-footer
      :inset="false"
      app
    >
      <span class="px-4">&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>

import NavigationMenu from './components/NavigationMenu';

export default {
  name: 'App',
  components: {
    NavigationMenu,
  },
  data: () => ({
    drawer: true,
    items: [
        { icon: 'mdi-home-group', text: 'Empreendimentos' },
        { icon: 'mdi-account-multiple', text: 'Usuários' },
      ],
  }),
  methods: {},
};
</script>
