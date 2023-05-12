import ContactComp from '/';
<template>
    <v-app id="contactForm">
    <v-sheet width="300" class="mx-auto">
      <v-form @submit.prevent>
        <v-text-field
          v-model="firstName"
          :rules="rules"
          label="First name"
        ></v-text-field>
        <v-text-field
          v-model="lastName"
          :rules="rules"
          label="Last name"
        ></v-text-field>
        <v-text-field
          v-model="email"
          :rules="rules"
          label="Email"
        ></v-text-field>
        <v-textarea clearable label="Label" prepend-icon="mdi-vuetify"></v-textarea>
        <v-btn type="submit" block class="mt-2">Submit</v-btn>
      </v-form>
    </v-sheet>
</v-app>
  </template>
<script>
export default {
    
}
</script>
<style scoped> 
#contactForm {
    padding-top: 20%;
}

</style>
