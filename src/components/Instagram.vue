<template>
  <v-row class="ma-0">
    <v-col cols="6" md="3" class="pa-0 box-instagram" v-for="(insta, i) in instagrams" :key="'insta' + i">
      <v-img
        :aspect-ratio="1"
        :src="insta.image"
      ></v-img>
      <div class="foreground">
        <dir class="content">
          <div>
            <v-icon color="black">
              mdi-instagram
            </v-icon>
          </div>
          <v-btn small color="black" class="mt-3 white--text" :to="link"> Buy Now </v-btn>
        </dir>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "Home",

  components: {
    //
  },

  data: () => ({
    instagrams: [
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
      {
        image: "https://cdn.shopify.com/s/files/1/1368/3463/products/CUTS-2020-08-06_ON-MODEL_25083.jpg?v=1626134493",
        link: "#",
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
.box-instagram {
  position: relative;
  cursor: pointer;
  .foreground {
    opacity: 0;
    position: absolute;
    top: 0;
    z-index: 1;
    width: 100%;
    height: 100%;
    background: #ffffff78;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
.box-instagram:hover .foreground{
  opacity: 1;
}
</style>