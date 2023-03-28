<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" elevate-on-scroll fixed app>
      <v-toolbar-title
      class="ml-16"
      >{{ title }}</v-toolbar-title>
      <v-text-field
        :rounded=true
        color="black"
        class="ml-8"
        hide-details="true"
        label="Search"
        :single-line=true
        clear-icon="mdi-close-circle"
        clearable
        rows="1"
        prepend-inner-icon="mdi-magnify"
        style="background: white;"
      ></v-text-field>
      <v-spacer />


      <v-btn text tile href="/login">Login</v-btn>
      <v-btn icon tile><v-icon  light> mdi-bell </v-icon ></v-btn>
      <v-btn icon tile><v-icon light> mdi-heart </v-icon></v-btn>
      <v-btn icon tile><v-icon light> mdi-cart </v-icon></v-btn>


      <v-btn class="mr-16" icon @click.stop="modalWindow = !modalWindow">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
        <Nuxt />
    </v-main>
    <v-navigation-drawer v-model="modalWindow" temporary center fixed>
      <v-list>
      </v-list>
    </v-navigation-drawer>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
        {
          icon: 'mdi-account-circle',
          title: 'Test',
          to: '/test',
        },
      ],
      miniVariant: false,
      right: false,
      modalWindow: false,
      title: 'TEST SITE',
    }
  },
}
</script>
