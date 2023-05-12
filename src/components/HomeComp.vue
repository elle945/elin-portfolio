<template lang="">
  <!-- Home -->
     <v-app id="home">
    <v-container fluid>
      <div class ="top"></div>
      <div class="head">
        <v-row>
          <v-col cols="5">
            <div id="top-t" style="position: relative" >
              <div v-for="user in users" :key="user.id" v-if="desiredId">
              <h1 class="text-white"> {{user.firstname}} {{user.lastname}} </h1>
              <span class="text-grey">{{user.career}}</span><br />
              </div>
              <v-btn tile dark class="bg-green" :to="{ name: 'contact' }"
        title="contact"
        value="contact" variant="elevated">
                Contact me
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </div>
      <!-- About -->
      <v-col cols="12" class="mt-16" id="about">
        <div>
          <v-row>
            <v-col cols="12" sm="12">
              <div class="text-lg-center pt-16">
              <p>_________________________________________________________________________________________</p>
            </div>
            
              <div class="text-h1 text-center pa-10  ">
            Projects
              </div>
              <!-- About Grid -->
              
              <v-item-group selected-class="bg-primary">
                <div class="egg" >
              </div>
    <v-container class="pt-12 container-with-egg">
      <v-row>
        <v-col
          v-for="user in users.slice(2, 10)"
          :key="user.id"
          cols="4"
          md="4"
        >
          <v-item v-slot="">
            <router-link to="#" >
            <v-card
              :class="['d-flex align-center', selectedClass]"
              dark
              height="100"
              @click="toggle">

            <v-card-text class="text-black">
              {{user.company}}
            </v-card-text>
            </v-card>
          </router-link>
          </v-item>
        </v-col>
      </v-row>
    </v-container>
  </v-item-group>
            </v-col>
          </v-row>
        </div>
      </v-col>
    </v-container>
   </v-app>
</template>
<script>
import jsonData from '../info.json'


export default {
    name: 'Home',
    props: {
    desiredId: {
      type: Number,
      required: true,

    },
  },
    data() {
        return {
            users: [],
            lorem: `Lorem ipsum dolor sit amet, mel at clita quando. Te sit oratio
       vituperatoribus, nam ad ipsum posidonium mediocritatem, explicari dissentiunt cu mea.
        Repudiare disputationi vim in, mollis iriure nec cu, alienum argumentum ius ad. Pri eu 
        justo aeque torquatos.`
        };
    },
  methods: {
    getData(){
       this.users = jsonData;
    
        }
  },
  created() {
    this.getData();
  }

    
}

</script>

<style scoped>

#top-t{
  padding-top: 60%;
}

#about > div > div > div {
  width: 100%;
}
.v-container {
  padding: 16px 0 16px 0;
}

.head {
  position: relative;
  text-align: center;
  padding: 12px;
  margin-top: -10%;
  margin-bottom: 6px;
  height: 100vh;
  width: 100%;
  color: green;
}
.head:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 50%;
  background: black;
  /* Shape */
  transform: skew(0deg, 6deg);
}
.head:after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 50%;
  background: black;
  transform: skew(0deg, -6deg);
}
.egg {
  position: absolute;
  top: -20%; 
  left: 50%; 
  transform: translate(-50%, -50%);
  width: 386px;
  height: 180px;
  background-color: #27E736; 
  opacity: 0.7;
  border-radius: 50% 50% 50% 50% / 60% 40% 60% 40%;
  z-index: -1; /* Ensures the egg appears behind other elements */
}
.container-with-egg {
  position: relative; /* Needed to establish the positioning context for the egg */
  margin: auto;
  
}


#about {
  padding-top: 10%;


}


</style>