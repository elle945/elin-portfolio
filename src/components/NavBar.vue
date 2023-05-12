<template>
    <v-app-bar app color="black" dark flat class="px-12" >
      <v-btn class="text-green">
         ELIN NILSSON
      </v-btn>
      
  
      <v-spacer></v-spacer>
      <v-btn text @click="scroll('home'), redirectToHome" >Home</v-btn>
      <v-btn text @click="scroll('about')"  >About</v-btn>
      <v-btn text 
      @click="redirectToContact"
        exact class="text-green" > Contact</v-btn>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    methods: {
      scroll(refName) {
        const element = document.getElementById(refName);
        element.scrollIntoView({ behavior: "smooth" });
      },
      redirectToContact() {
      this.$router.push('/contact');
    },
    redirectToHome() {
      this.$router.push('/');
      
    },
    },
  };
  </script>
