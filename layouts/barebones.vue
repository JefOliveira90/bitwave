<template>
  <v-app>

    <!-- Toolbar -->
    <v-app-bar
      app
      text
      dark
      dense
      fixed
      color="#212121"
    >
      <v-toolbar-title class="ml-0">
        <v-btn
          to="/"
          depressed
          text
          exact
          id="logo"
          exact-active-class="app-title-active"
          class="text-none title px-2"
        >{{ title }}</v-btn>
      </v-toolbar-title>

      <v-spacer />

      <notifications />

      <user-menu class="ml-2" />

    </v-app-bar>

    <!-- Content -->
    <v-content style="max-height: 100vh">

      <nuxt />

    </v-content>

  </v-app>
</template>

<script>
  import Notifications from '~/components/Notifications'
  import UserMenu from '@/components/SubLayout/UserMenu'

  export default {
    components: {
      Notifications,
      UserMenu,
    },

    data () {
      return {
        title: '[bitwave.tv]',
        dark: true,
        clipped: false,
      }
    },
  }
</script>

<style lang="scss" scoped>
  html {
    overflow-y: auto !important;
  }

  #logo.app-title-active {
    &:hover::before {
      opacity: 0.24;
    }

    &::before {
      opacity: 0;
    }
  }
</style>
