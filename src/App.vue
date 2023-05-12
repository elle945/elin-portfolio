<template>
  <v-app>
    <NavBar/>
    <div id="app">
    <router-view />
  </div>
  </v-app>
</template>

<script>
import NavBar from './components/NavBar.vue';


export default {
  name: 'App',

  components: {
    NavBar,

},

}
</script>

