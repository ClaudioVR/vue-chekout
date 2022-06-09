<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="100"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Vue Checkout Form
        </h1>

        <p class="mt-5 subheading font-weight-regular">
          Combining Vue.js and Vuetify to create a mock checkout.
          <br>Check out my code on 
          <a
            href="https://github.com/ClaudioVR?tab=repositories"
            target="_blank"
          >Github</a>
        </p>
      </v-col>

    

      
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data: () => ({
     // no data 
    }),
  }
</script>
