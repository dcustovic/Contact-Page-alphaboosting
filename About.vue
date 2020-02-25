<template>
  <div class="about-page">
    <div class="about-page-bg"></div>
    <div class="about-page-content">

      <!-- NASLOV -->
      <section>
        <v-col class="mt-4 pb-4">
          <div class="text-center">
            <h1 class="heading">
              <b>About us</b>
            </h1>
            <span class="subheading">Meet us and our professional team</span>
          </div>
        </v-col>
      </section>
      <!-- NASLOV -->

    <!-- EMAIL FORM -->
      <v-row class="justify-center">
        <v-col xs="12" sm="8" md="4">
       
            <v-card-text >   
              <v-form class="px-3" ref="form">
                <v-text-field label="Name" v-model="name" :error-messages="nameErrors" prepend-icon="fad fa-user"
                required @input="$v.name.$touch()" @blur="$v.name.$touch()"></v-text-field> <!-- za v-text-field imamo prepend-icon -->
                
                <v-text-field label="Email" v-model="email" :error-messages="emailErrors" prepend-icon="fad fa-at"
                required @input="$v.email.$touch()" @blur="$v.email.$touch()"></v-text-field>
                
                <v-text-field label="Subject" v-model="subject" prepend-icon="fas fa-pen-alt"></v-text-field>
                
                <v-textarea label="Message" v-model="message" prepend-icon="fas fa-comment-alt"></v-textarea> <!-- za v-text-area imamo prepend-icon -->
              </v-form>

              <!-- Submit btn -->
                <v-layout justify-center>
                    <v-btn color="primary" @click="submit" :loading="loading">Submit</v-btn>    
                </v-layout>
              <!-- Submit btn -->
            </v-card-text>
         
        </v-col>
      </v-row>
    <!-- EMAIL FORM -->


<!-- OSTACI

      <v-container fluid>
        <v-row class="justify-start">
          <v-col xs="12" sm="5">
            <v-card flat class="transparent pa-2">
              <v-card-text class="text-center">
                <v-icon x-large color="primary">fa fa-gamepad</v-icon>
              </v-card-text>
              <v-card-title class="headline justify-center">Professional players</v-card-title>
              <v-card-text class="text-center">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias, natus. Iusto provident inventore,
                debitis aliquid ex cumque in placeat, voluptatum alias consectetur quia molestias, aliquam
                exercitationem maxime explicabo vitae.
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row class="justify-start">
          <v-col xs="12" sm="5">
            <v-card flat class="transparent pa-2">
              <v-card-text class="text-center">
                <v-icon x-large color="primary">fa fa-brain</v-icon>
              </v-card-text>
              <v-card-title class="headline justify-center">Tactical gaming</v-card-title>
              <v-card-text class="text-center">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias, natus. Iusto provident inventore,
                debitis aliquid ex cumque in placeat, voluptatum alias consectetur quia molestias, aliquam
                exercitationem maxime explicabo vitae.
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row class="justify-start">
          <v-col xs="12" sm="5">
            <v-card flat class="transparent pa-2">
              <v-card-text class="text-center">
                <v-icon x-large color="primary">fa fa-expand-arrows-alt</v-icon>
              </v-card-text>
              <v-card-title class="headline justify-center">Smart moves</v-card-title>
              <v-card-text class="text-center">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias, natus. Iusto provident inventore,
                debitis aliquid ex cumque in placeat, voluptatum alias consectetur quia molestias, aliquam
                exercitationem maxime explicabo vitae.
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
-->


        <v-divider></v-divider>
        
        <v-container> 
          <v-row class="justify-center" >
            <v-col cols="6" md="5">
              <v-card flat class="transparent" width="620">
                <v-card-text class="text-center"></v-card-text>
                <v-card-title class="headline justify-center">Team info</v-card-title>
                <v-card-text class="text-center" > 
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias, natus. Iusto provident inventore,
                  debitis aliquid ex cumque in placeat, voluptatum alias consectetur quia molestias, aliquam
                  exercitationem maxime explicabo vitae.
                </v-card-text>
              </v-card>
            </v-col>
            
           
            <v-col cols="6" md="5">
              <v-card flat class="transparent">
                <v-card-text class="text-center"></v-card-text>
                <v-card-title class="headline justify-center">Contact us</v-card-title>
                <v-card-text class="text-center">We are looking forward to meet you!</v-card-text>
                
                <v-card-title class="justify-center">
                  <v-list class="transparent">
                    <v-list-item>
                      <v-list-item-action>
                        <v-icon color="primary">fa fa-phone</v-icon>
                      </v-list-item-action>
                      <v-list-item-content>
                        <v-list-item-title>777-867-5309</v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>

                    <v-list-item>
                      <v-list-item-action>
                        <v-icon color="primary">fa fa-map-marker</v-icon>
                      </v-list-item-action>
                      <v-list-item-content>
                        <v-list-item-title>Zagreb, Croatia</v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>

                    <v-list-item>
                      <v-list-item-action>
                        <v-icon color="primary">fa fa-envelope</v-icon>
                      </v-list-item-action>
                      <v-list-item-content>
                        <v-list-item-title>info@alphaboosting.com</v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-list>
                </v-card-title>

              </v-card>
            </v-col>
           </v-row>
         </v-container>
    </div>
  </div>
</template>


<script>
import { required, minLength, email } from 'vuelidate/lib/validators'

export default {
  metaInfo: {
    title: "About",
    titleTemplate: "%s - Alphaboosting",
    // Define meta tags here.
    meta: [
      { httpEquiv: "Content-Type", content: "text/html; charset=utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Learn more about our Alphaboosting team and professional players."
      },
      { name: "robots", content: "index, follow" }
    ]
  },
  data() {
    return{
      name: '',
      email: '',
      subject: '',
      message: ''
    } 
  },
  validations: {
      name: { required, minLength: minLength(3) },
      email: { required, email }
  },
  methods: {
      submit () {
        this.$v.$touch()  // spriječava da korisnik stisne Submit kada je input prazan
      }
  },
  computed: {
      nameErrors () {
        const errors = []
        if (!this.$v.name.$dirty) return errors;
          !this.$v.name.required && errors.push('Name is required.');
          !this.$v.name.minLength && errors.push('Minimum of 3 characters.');
          return errors;
      },
      emailErrors () {
      const errors = []
        if (!this.$v.email.$dirty) return errors;
          !this.$v.email.email && errors.push('Must be valid e-mail address.');
          !this.$v.email.required && errors.push('E-mail is required.');
          return errors;
    }
  }
};
</script>


<style lang="scss">
h1 {
  font-size: 160%;
}
.about-page {
  font-family: $main-font !important;
}
.about-page-bg {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  z-index: 0;
  background-image: url("./../assets/img/brawl-stars-pattern.png");
  background-repeat: repeat;
  background-size: 200px auto;
  opacity: 0.4;
}
.about-page-content > section {
  position: relative;
  z-index: 100;
}
</style>