<template>
  <div>
    <section>
      <slide-hero></slide-hero>
    </section>

    <section class="section py-15">
      <v-container class="content-text text-center">
        <div class="caption text-caption text-decoration-underline mb-3">OUR MISSION</div>
        <div class="title font-weight-bold text-h4">
          We're here to outfit the world’s most ambitious people.
        </div>
      </v-container>
    </section>

    <section>
      <v-row>
        <v-col md="6">
          <image-text-bottom-left 
            title="Best Sellers" 
            link="#" 
            ratio="1"
            image="https://images.ctfassets.net/gm2gqumrpcat/1yj4ZsoZiKJakpV1osWtiJ/a4744c5989c80d9c1cfa846cdf2e8a01/HP-Block-best-seller.jpg?w=600&h=600&q=50">
          </image-text-bottom-left>
        </v-col>
        <v-col md="6">
          <image-text-bottom-left 
            title="Summer 2021" 
            link="#" 
            ratio="1"
            image="https://images.ctfassets.net/gm2gqumrpcat/3rBdLmrZ7PkD2o2x8PfYWk/8199409ebf6d9e19c79b5634d984d4f1/HP-Block-Summer21.jpg?w=1500&h=1500&q=50">
          </image-text-bottom-left>
        </v-col>
      </v-row>
    </section>

    <section class="section py-15">
      <v-container class="text-center">
        <div class="title text-h6 font-weight-bold mb-10">Best Seller</div>

        <v-row>
          <v-col md="4">
            <product></product>
          </v-col>
          <v-col md="4">
            <product></product>
          </v-col>
          <v-col md="4">
            <product></product>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <section>
      <v-row>
        <v-col md="12">
          <image-text-bottom-left 
            title="New Release" 
            link="#" 
            ratio="3"
            image="https://images.ctfassets.net/gm2gqumrpcat/2AUNfELZiGUbDstCR2rLbR/6aecc5f58caebfdc7721646dc03f9954/HP-Middle-Unit-summer21-new-releases.jpg?w=1200&h=480&q=50">
          </image-text-bottom-left>
        </v-col>
      </v-row>
    </section>

    <section class="section py-15">
      <v-container class="text-center">
        <div class="title text-h6 font-weight-bold mb-10">Instagram</div>

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
  }
</script>

<style>
  .content-text{
    width: 600px;
  }
  .cursor-pointer{
    cursor: pointer;
  }
</style>