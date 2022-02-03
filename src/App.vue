<template>
  <v-app>
    <v-app-bar
      app
      flat
    >
     <Header/>
    </v-app-bar>

    <v-content>
      <Hero/>
       <!-- <Popup/> -->
    </v-content>
    <v-layout column align-center>
      <v-flex class= "mt-8 mb-10">
        <Popup/>
      </v-flex>
    </v-layout>
  </v-app>
</template>

<script>

import Header from './components/Header';
import Hero from './components/Hero';
import Popup from './components/Popup';

export default {
  name: 'App',

  components: {
    Header,
    Hero,
    Popup
  },
};
</script>
