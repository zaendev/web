<template>
  <div>
    <section>
      <slide-hero></slide-hero>
    </section>

    <section :class="$vuetify.breakpoint.smAndDown ? 'section py-5 pb-2':'section py-15'">
      <v-container class="content-text text-center">
        <div class="caption text-caption text-decoration-underline mb-3">ABOUT TUFT</div>
        <div :class="$vuetify.breakpoint.smAndDown ? 'title font-weight-bold text-h5' : 'title font-weight-bold text-h4'">
          TUFT had developed over the years by working closely with the hairdressers, beauty therapists and our distributors worldwide.
        </div>
      </v-container>
    </section>

    <section>
      <v-container fluid>
      <v-row>
        <v-col cols="12" sm="6">
          <image-text-bottom-left 
            title="Best Sellers" 
            link="#" 
            ratio="1"
            image="https://element9.solindo.com/img-tuft/8005-Settings3.jpg">
          </image-text-bottom-left>
        </v-col>
        <v-col cols="12" sm="6">
          <image-text-bottom-left 
            title="Summer 2021" 
            link="#" 
            ratio="1"
            image="https://element9.solindo.com/img-tuft/Play-Tuft-Catalogue_Patel.jpg">
          </image-text-bottom-left>
        </v-col>
      </v-row>
      </v-container>
    </section>

    <section :class="$vuetify.breakpoint.smAndDown ? 'section py-5':'section py-15'">
      <v-container class="text-center">
        <div :class="$vuetify.breakpoint.smAndDown ? 'title text-h6 font-weight-bold mb-3' : 'title text-h6 font-weight-bold mb-10'">Best Seller</div>

        <v-row class="scroll-product-mobile">
          <v-col cols="10" sm="4" md="3" v-for="(product, i) in products" :key="'product' + i">
            <product :title="product.title" :price="product.price" :image="product.image" :tag="product.tag"></product>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <section>
      <v-container fluid>
      <v-row>
        <v-col md="12">
          <image-text-bottom-left 
            title="New Release" 
            link="#" 
            ratio="3"
            image="https://element9.solindo.com/img-tuft/8005-HD-2.jpg">
          </image-text-bottom-left>
        </v-col>
      </v-row>
      </v-container>
    </section>

    <section :class="$vuetify.breakpoint.smAndDown ? 'section py-5 pb-0':'section py-15 pb-0'">
      <v-container fluid class="text-center">
        <div :class="$vuetify.breakpoint.smAndDown ? 'title text-h6 font-weight-bold mb-3':'title text-h6 font-weight-bold mb-10'">@tuftintl</div>

        <instagram></instagram>
      </v-container>
    </section>
  </div>
</template>

<script>
  import SlideHero from '../components/SlideHero'
  import ImageTextBottomLeft from '../components/ImageTextBottomLeft'
  import Product from '../components/Product'
  import Instagram from '../components/Instagram'
  export default {
    name: 'Home',

    components: {
      SlideHero,
      ImageTextBottomLeft,
      Product,
      Instagram
    },

    data: () => ({
      products: [
        {
          title: 'TUFT 8005 Galaxy Professional Hair Dryer',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Tuft-Galaxy-A-360x360.jpg',
          tag: 'New'
        },
        {
          title: 'TUFT 8601 Classic Professional Hair Dryer',
          price: '150',
          image: 'https://element9.solindo.com/img-tuft/8601S1-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 8602 Lightweight Professional Hair Dryer',
          price: '120',
          image: 'https://element9.solindo.com/img-tuft/8602-SUS-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 1" Diamond Styling Iron',
          price: '172',
          image: 'https://element9.solindo.com/img-tuft/6600-2_S-360x360.jpg',
          tag: 'Best Seller'
        }
      ],
    })
  }
</script>

<style>
  .content-text{
    width: 1000px;
  }
  @media (max-width: 991.98px) {
    .content-text{
      width: 375px;
    }
  }
  .cursor-pointer{
    cursor: pointer;
  }
</style>