<template>
  <div class="slide-hero">
    <v-img src="https://element9.solindo.com/img-tuft/TUFT-BANNER-1920x1000.jpg" height="560" class="grey darken-4" style="position: relative">
      <div class="box-content">
        <div class="content">
          <div class="text">
            <h1 class="
                transition-swing
                text-h4
                font-weight-bold
                white--text
                text-center
              ">
              POWER OF INNOVATION
            </h1>
          </div>
          <v-btn large outlined color="white" to="/collections" class="mt-5"> Shop Now </v-btn>
        </div> 
      </div>
    </v-img>
  </div>
</template>

<script>
  export default {
    name: "Home",

    components: {
      //
    },
  };
</script>

<style lang="scss" scoped>
  .slide-hero {
    .box-content {
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      .content {
        text-align: center;
        width: 400px;
      }
    }
  }
</style>