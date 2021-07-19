<template>
  <v-row class="ma-0 scroll-product-mobile">
    <v-col cols="10" md="3" class="pa-0 box-instagram" v-for="(insta, i) in instagrams" :key="'insta' + i">
      <v-img
        :aspect-ratio="1"
        :src="insta.image"
      ></v-img>
      <div class="foreground">
        <dir class="content">
          <div>
            <v-icon large color="black">
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
  props: [
    'link',
    'image'
  ],
  components: {
    //
  },

  data: () => ({
    instagrams: [
      {
        image: "https://element9.solindo.com/img-tuft/14156508_1045751618877971_1684864984_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/14262798_601504423364164_456762347_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/13743279_1227771227257016_2074654691_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/13737007_1750124951925129_553349971_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/13737007_1750124951925129_553349971_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/14156508_1045751618877971_1684864984_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/14262798_601504423364164_456762347_n.jpg",
        link: "#",
      },
      {
        image: "https://element9.solindo.com/img-tuft/14262798_601504423364164_456762347_n.jpg",
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