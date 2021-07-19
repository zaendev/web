<template>
  <v-container fluid :class="$vuetify.breakpoint.mdAndUp ? 'px-7': ''">
    <section class="mt-10">
      <v-row>
        <v-col md="7" class="d-flex">
          <div class="thumbnail d-flex flex-column">
            <div class="mb-2 mr-2 cursor-pointer" @click="changeImage(image)" v-for="(image, i) in images"
              :key="'image' + i">
              <v-img :class="showImage == image ? 'active' : ''" :aspect-ratio="1" width="70" :src="image"></v-img>
            </div>
          </div>
          <div class="show-image w-100">
            <v-img :aspect-ratio="1"
              :src="showImage ? showImage : 'https://element9.solindo.com/img-tuft/5000-Turbo+_S-800x800.jpg'">
            </v-img>
          </div>
        </v-col>
        <v-col md="5">
          <v-chip class="ma-2 ml-0" small outlined>
            TUFT 8005
          </v-chip>
          <h1 :class="$vuetify.breakpoint.mdAndUp ? '':'text-h6'">TUFT 8005 Turbo Professional Hair Dryer</h1>
          <div class="rating mb-3">
            <v-rating
              v-model="rating"
              color="yellow darken-3"
              background-color="grey darken-1"
              empty-icon="$ratingFull"
              half-increments
              hover
              small
            ></v-rating>
            
          </div>
          <div class="short-description">
            <p>TURBO, the hairdryer that gives you the speed and heat you ever desire. 
              TUFT 8005 Professional hairdryer has a 2200W AC Motor with a high-pressure zig zag heating element to deliver intense power with super sleek finishes. 
              TUFT 8005 Turbo Hair Dryer has a built-in Ultrafine Ionic Technology to reduce the amount of static electricity build-up in the hair for maximum shine and frizz reduction. </p>
          </div>

          <div class="filter-product-show">
            <div class="d-flex mb-3">
              <div>
                <div class="label">COLOR</div>
                <div>
                  <v-chip-group style="flex-wrap: wrap;">
                    <v-chip v-for="(color, i) in colors" :key="'color' + i" filter outlined label class="py-5 pr-5">
                      <v-avatar :style="
                          'border: 1px solid; background-color: ' + color.code
                        " size="20" class="mr-2">
                      </v-avatar>
                      {{ color.name }}
                    </v-chip>
                  </v-chip-group>
                </div>
              </div>
            </div>
            <div class="d-flex mt-6 box-price">
              <div class="d-flex align-center w-100">
                <div class="price">
                  <span class="symbol">$</span>
                  150
                </div>
                <div class="ml-7 box-btn">
                  <v-btn x-large color="black" class="white--text" block>Add to Cart</v-btn>
                </div>
              </div>
            </div>
            <div class="d-flex mt-10">
              <v-expansion-panels class="expand-dense px-0" accordion flat multiple>
                <v-expansion-panel>
                  <v-expansion-panel-header class="text-h6 px-0 py-2"> Features </v-expansion-panel-header>
                  <v-expansion-panel-content>
                    <b>2200W AC MOTOR</b>
                    <p>With high-pressure zigzag heating element to deliver intense power with super sleek finishes.</p>
                    <b>BUILT-IN ULTRAFINE IONIC TECHNOLOGY</b>
                    <p>To reduce the amount of static electricity build-up in the hair for maximum shine and frizz reduction</p>
                    <b>3 TEMPERATURE SETTINGS, 2 SPEED SETTINGS AND COOL SHOT</b>
                    <p>To lock in styles and promotes luster.</p>
                    <b>ERGONOMIC DESIGN</b>
                    <p>For easy hold and maneuver, double-blade reduces muscle strain for longer use.</p>
                    <b>COMES WITH 2 DETACHABLE CONCENTRATOR NOZZLES</b>
                    <p>For easy styling.</p>
                  </v-expansion-panel-content>
                </v-expansion-panel>
                <v-expansion-panel>
                  <v-expansion-panel-header class="text-h6 px-0 py-2"> Specification </v-expansion-panel-header>
                  <v-expansion-panel-content>
                    <table>
                      <tbody>
                        <tr>
                          <td>Product Model</td>
                          <td class="pl-3"> 8005</td>
                        </tr>
                        <tr>
                          <td>Finishing/Color</td>
                          <td class="pl-3"> Matte Black</td>
                        </tr>
                        <tr>
                          <td>Voltage</td>
                          <td class="pl-3"> 220-240V 50/60Hz </td>
                        </tr>
                        <tr>
                          <td>Watt</td>
                          <td class="pl-3"> 2200W - 2400W</td>
                        </tr>
                        <tr>
                          <td>Weight</td>
                          <td class="pl-3"> 590g</td>
                        </tr>
                        <tr>
                          <td>Motor</td>
                          <td class="pl-3"> Premium AC</td>
                        </tr>
                        <tr>
                          <td>Airflow</td>
                          <td class="pl-3"> 21000m/s</td>
                        </tr>
                        <tr>
                          <td>Temperature</td>
                          <td class="pl-3">  Avg 110°C - 120°C <br>
                          3 Temperature & 2 Speed </td>
                        </tr>
                        <tr>
                          <td>Functions</td>
                          <td class="pl-3">
                            Setting, Cool Shot
                          </td>
                        </tr>
                        <tr>
                          <td>Technology</td>
                          <td class="pl-3">Ultrafine Ionic <br>
                            Professional Use, Lightweight,</td>
                        </tr>
                        <tr>
                          <td>Benefits</td>
                          <td class="pl-3">
                            Fast Drying, Energy Saving, <br>
                             Ergonomic Design
                          </td>
                        </tr>
                      </tbody>
                    </table>
                  </v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </div>
          </div>
        </v-col>
      </v-row>
    </section>

    <section>
      <v-container fluid>
        <v-row>
          <v-col md="12">
            <v-img 
              src="https://element9.solindo.com/img-tuft/8005-HD-2.jpg" 
              aspect-ratio="3" 
              class="grey darken-4">
            </v-img>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <section :class="$vuetify.breakpoint.smAndDown ? 'mt-5':'mt-15'">
      <v-container fluid class="text-center">
        <div class="title text-h6 font-weight-bold mb-10">Related Products</div>
    
        <v-row class="scroll-product-mobile">
          <v-col cols="10" sm="4" md="3" v-for="(product, i) in products" :key="'product' + i">
            <product :title="product.title" :price="product.price" :image="product.image" :tag="product.tag"></product>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </v-container>
</template>

<script>
  import Product from "../components/Product";
  export default {
    name: "Collection",

    components: {
      Product
    },

    data: () => ({
      rating: 4,
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
          name: "Blue",
          code: "#3f51b5",
        },
        // {
        //   name: "Mountain Mist",
        //   code: "#a98f86",
        // },
      ],
      images: [
        'https://element9.solindo.com/img-tuft/5000-Turbo+_S-800x800.jpg',
        'https://element9.solindo.com/img-tuft/5000-Turbo+_F-800x800.jpg',
        'https://element9.solindo.com/img-tuft/5000-Turbo+_B-800x800.jpg',
        'https://element9.solindo.com/img-tuft/5000-Turbo+_FL-800x800.jpg'
      ],
      showImage: '',
      products: [
        {
          title: 'TUFT 7008 Professional Curling Iron 19mm',
          price: '155',
          image: 'https://element9.solindo.com/img-tuft/Spincurl-Curling-Iron-19mm-S-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 1888 Featherlight Professional Hair Dryer',
          price: '150',
          image: 'https://element9.solindo.com/img-tuft/1888-Featherlight_2-360x360.jpg',
          tag: ''
        },
        {
          title: 'TUFT 2" Diamond Styling Iron',
          price: '186',
          image: 'https://element9.solindo.com/img-tuft/6600-2_S-360x360.jpg',
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

    methods: {
      changeImage(img) {
        this.showImage = img
      }
    }
  };
</script>

<style lang="scss" scoped>
  .thumbnail {
    width: 60px !important;

    .v-image {
      &.active {
        border: 1px solid;
      }
    }
  }

  .filter-product-show {
    .number {
      font-size: 10px;
      color: #c7c7c7;
    }

    .label {
      font-size: 10px;
      font-weight: 700;
    }

    .box-price {
      .price {
        width: 120px;
        font-size: 60px;
        font-weight: 500;
        padding-left: 17px;
        position: relative;
        line-height: normal;

        .symbol {
          position: absolute;
          font-size: 26px;
          top: 0;
          left: 0;
          font-weight: 300;
        }
      }

      .box-btn {
        width: 100%;
      }
    }
  }
</style>