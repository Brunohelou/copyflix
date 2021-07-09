<template>
<div>
  <v-app dark>

    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
     
    
  
      <v-toolbar-title v-text="title" class="red--text mytitle" />
      <v-spacer />
    
    </v-app-bar>



    
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</div>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
      
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Netflix'
    }
  }
}
</script>
<style scoped>
  .mytitle {
    font-size: 1.8rem;
  }
</style>