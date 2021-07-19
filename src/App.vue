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

<style>
  .w-100{
    width: 100%;
  }
  @media (max-width: 768px) {
    .scroll-product-mobile{
      flex-flow: row!important;
      overflow-x: scroll!important;
    }
  } 
  .v-expansion-panel-content__wrap {
    padding: 0!important;
  }
</style>