<template>
  <div class="slide-hero">
    <v-img src="https://images.ctfassets.net/gm2gqumrpcat/54Oh2GnfkNp3dlcygmJJC5/c4b026af124828564cf7687ed8b39feb/best-sellers-restock-desktop-hero-sage.jpg?w=2400&h=800&q=50&fm=webp" height="560" class="grey darken-4" style="position: relative">
      <div class="box-content">
        <div class="content">
          <div class="text">
            <h1 class="
                transition-swing
                text-h3
                font-weight-bold
                white--text
                text-center
              ">
              BEST SELLERS RESTOKED
            </h1>
          </div>
          <v-btn large outlined color="white" class="mt-5"> Shop Now </v-btn>
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