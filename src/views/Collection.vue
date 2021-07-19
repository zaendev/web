<template>
  <div>
    <section>
      <div class="banner-hero">
        <v-img
          src="@/assets/banner-collection.png"
          :aspect-ratio="$vuetify.breakpoint.smAndDown ? 2 : 5"
          class="grey darken-4"
          style="position: relative"
        >
          <div class="box-content">
            <div class="content">
              <div class="text">
                <h1
                  :class="$vuetify.breakpoint.smAndDown ? 'transition-swing text-h5 font-weight-bold white--text text-center':'transition-swing text-h4 font-weight-bold white--text text-center'"
                >
                  ALL PRODUCTS
                </h1>
              </div>
            </div>
          </div>
        </v-img>
      </div>
    </section>

    <section :class="$vuetify.breakpoint.mdAndUp ? 'section content my-15' : 'section content'">
      <v-container fluid :class="$vuetify.breakpoint.mdAndUp ? 'pr-6' : ''">
        <v-row>
          <v-col cols="12" md="2" v-if="$vuetify.breakpoint.mdAndUp">
            <v-list dense>
              <v-list-item-group color="primary">
                <v-list-item v-for="(item, i) in categories" :key="i">
                  <v-list-item-content>
                    <v-list-item-title v-text="item"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>

            <v-expansion-panels
              hover
              class="expand-dense"
              accordion
              flat
              multiple
              v-model="openPanel"
            >
              <!-- <v-expansion-panel>
                <v-expansion-panel-header> Gender </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-checkbox
                    v-for="(gender, i) in genders"
                    :key="'gender' + i"
                    v-model="selectedGender"
                    :label="gender"
                    hide-details
                  ></v-checkbox>
                </v-expansion-panel-content>
              </v-expansion-panel> -->
              <!-- <v-expansion-panel>
                <v-expansion-panel-header> Size </v-expansion-panel-header>
                <v-expansion-panel-content>
                  <v-chip-group v-model="selectSize" column multiple>
                    <v-chip
                      filter
                      outlined
                      label
                      v-for="(size, i) in sizes"
                      :key="'size' + i"
                    >
                      {{ size }}
                    </v-chip>
                  </v-chip-group>
                </v-expansion-panel-content>
              </v-expansion-panel> -->
              <v-expansion-panel>
                <v-expansion-panel-header> Colour </v-expansion-panel-header>
                <v-expansion-panel-content class="px-5">
                  <v-item-group multiple>
                    <v-row class="mt-1">
                      <v-col
                        v-for="(color, i) in colors"
                        :key="'color' + i"
                        cols="4"
                        md="4"
                        class="pa-1 mb-2"
                      >
                        <v-item v-slot="{ active, toggle }">
                          <div class="text-center">
                          <v-avatar 
                            :style="'border: 1px solid; background-color: ' + color.code" 
                            size="28" 
                            @click="toggle">
                            <v-scroll-y-transition>
                              <div v-if="active">
                                <v-icon :color="color.code == '#fff' ? 'black' : 'white'">mdi-check</v-icon>
                              </div>
                            </v-scroll-y-transition>
                          </v-avatar>
                          <div style="font-size: 10px" class="mt-1">{{ color.name }}</div>
                          </div>
                        </v-item>
                      </v-col>
                    </v-row>
                  </v-item-group>
                </v-expansion-panel-content>
              </v-expansion-panel>
              <v-expansion-panel class="mt-3">
                <v-expansion-panel-header> Price </v-expansion-panel-header>
                <v-expansion-panel-content class="px-5">
                  <vue-slider v-model="price" />
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-col>
          <v-col cols="12" md="10">
            <v-row v-if="$vuetify.breakpoint.smAndDown">
              <v-col>
                <v-chip-group>
                  <v-chip pill :value="i" filter class="font-weight-medium" outlined v-for="(category, i) in categories" :key="'itemcat' + i">
                      {{ category }}
                    </v-chip>
                  </v-chip-group>
                </v-col>
              </v-row>
            <v-row>
              <v-col cols="6" sm="4" md="3" v-for="(product, i) in products" :key="'product' + i">
                <product :title="product.title" :price="product.price" :image="product.image" :tag="product.tag"></product>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
import Product from "../components/Product";
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/antd.css'

export default {
  name: "Collection",

  components: {
    Product,
    VueSlider
  },

  data: () => ({
    price: [1, 100],
    openPanel: [0, 1, 2, 3, 4, 5],
    categories: [
      "Hair Dryer",
      "Flat Iron",
      "Curling Iron",
      "Hair Styler",
      "Hair Brush",
      "Beauty Machine",
      "Hair Accessories",
    ],
    // genders: ["Men", "Women", "Unisex"],
    // selectedGender: [],
    // sizes: [
    //   "3.5",
    //   "4",
    //   "4.5",
    //   "5",
    //   "5.5",
    //   "6",
    //   "6.5",
    //   "7",
    //   "7.5",
    //   "8",
    //   "8.5",
    //   "9",
    //   "9.5",
    //   "10",
    //   "10.5",
    //   "11",
    //   "11.5",
    //   "12",
    //   "12.5",
    //   "13",
    //   "13.5",
    //   "14",
    //   "15",
    //   "16",
    //   "17",
    //   "18",
    // ],
    // selectSize: [],
    colors: [
      {
        name: "Black",
        code: "#000",
      },
      {
        name: "White",
        code: "#fff",
      },
      {
        name: "Laurel Oak",
        code: "#8a8369",
      },
      {
        name: "Mountain Mist",
        code: "#a98f86",
      },
      {
        name: "Sage",
        code: "#7d867f",
      },
      {
        name: "Vintage",
        code: "#556472",
      },
      {
        name: "Mirage",
        code: "#b8c7d2",
      },
      {
        name: "Sunset",
        code: "#e69677",
      },
      {
        name: "Coyote",
        code: "#898774",
      },
      {
        name: "Granite",
        code: "#b1afb4",
      },
      {
        name: "Pacific Mist",
        code: "#c4d3cf",
      },
    ],
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
        },
        {
          title: 'TUFT DIAMOND CURL BAR',
          price: '130',
          image: 'https://element9.solindo.com/img-tuft/CURL-BAR-S-360x360.jpg',
          tag: 'New'
        },
        {
          title: 'TUFT 2" DIAMOND STYLING IRON',
          price: '186',
          image: 'https://element9.solindo.com/img-tuft/6600-2_S-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 8005 GALAXY PROFESSIONAL HAIR DRYER',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Tuft-Galaxy-A-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 8005 Galaxy Professional Hair Dryer',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Tuft-Galaxy-A-360x360.jpg',
          tag: 'New'
        },
        {
          title: 'TUFT 8602 LIGHTWEIGHT PROFESSIONAL HAIR DRYER',
          price: '120',
          image: 'https://element9.solindo.com/img-tuft/8602-SUS-360x360.jpg',
          tag: 'New'
        },
        {
          title: 'TUFT CHROMOMIST WITH OZONE',
          price: '186',
          image: 'https://element9.solindo.com/img-tuft/TUFT-Chromomist-with-Ozone-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 8005 GALAXY PROFESSIONAL HAIR DRYER',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Tuft-Galaxy-A-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 8005 Galaxy Professional Hair Dryer',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Tuft-Galaxy-A-360x360.jpg',
          tag: 'New'
        },
      ],
  }),
};
</script>

<style lang="scss" scoped>
.banner-hero {
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
.expand-dense {
  .v-expansion-panel-header {
    min-height: 40px;
    padding: 8px 16px;
  }
  .v-expansion-panel-content {
    .v-expansion-panel-content__wrap {
      padding: 8px 16px !important;
    }
  }
}
</style>