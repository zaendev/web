<template>
  <v-app>
    <navbar />
    <v-main>
      <router-view />
    </v-main>
    <footer-component />
  </v-app>
</template>

<script>
import FooterComponent from "./components/Footer";
import Navbar from "./components/Navbar";
export default {
  name: "App",

  components: {
    Navbar,
    FooterComponent,
  },
};
</script>