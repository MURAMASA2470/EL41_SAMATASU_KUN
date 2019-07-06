<template>
  <v-app light>
   
    <v-content>
      <!-- <v-container> -->
        <nuxt />
      <!-- </v-container> -->
    </v-content>
    <!-- <v-footer
      :fixed="fixed"
      app
    >
    </v-footer> -->
  </v-app>
</template>

<style>
  .v-btn {
    color: white !important;
    font-weight: 900;
    font-size: 1.25rem;
    width: 80vw;
    height: 50px;
    margin: 0 40px;
  }
</style>


<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
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
