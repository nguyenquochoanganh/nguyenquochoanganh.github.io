<template>
  <v-app dark>
    <v-main>
        <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'About',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'Portfolio',
          to: '/'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
