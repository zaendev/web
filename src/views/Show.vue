<template>
  <v-container fluid :class="$vuetify.breakpoint.mdAndUp ? 'px-7': ''">
    <section>
      <div :class="$vuetify.breakpoint.mdAndUp ? 'header-show py-7 d-flex align-center' : 'header-show py-2'">
        <div>
          <h1 :class="$vuetify.breakpoint.mdAndUp ? '':'text-h6'">CHEVRONS TEE</h1>
        </div>
        <v-spacer v-if="$vuetify.breakpoint.mdAndUp"></v-spacer>
        <div v-if="$vuetify.breakpoint.mdAndUp">
          <v-chip-group>
            <v-chip filter outlined label class="py-5 pr-5">
              <!-- <v-avatar color="primary" size="56" class="mr-2"></v-avatar> -->
              Elevator
            </v-chip>
            <v-chip filter outlined label class="py-5 pr-5">
              <!-- <v-icon right class="mr-2"> mdi-account-circle-outline </v-icon> -->
              Washer / Dryer
            </v-chip>
            <v-chip filter outlined label class="py-5 pr-5">
              <!-- <v-icon right class="mr-2"> mdi-account-circle-outline </v-icon> -->
              Fireplace
            </v-chip>
            <v-chip filter outlined label class="py-5 pr-5">
              <!-- <v-icon right class="mr-2"> mdi-account-circle-outline </v-icon> -->
              Wheelchair access
            </v-chip>
          </v-chip-group>
        </div>
      </div>

      <v-divider />
    </section>

    <section class="mt-10">
      <v-row>
        <v-col md="8">
          <div class="show-image">
            <v-img
              :aspect-ratio="3/2"
              :src="showImage ? showImage : 'https://static.nike.com/a/images/t_PDP_1280_v1/f_auto,q_auto:eco/a47b2ef9-8239-4e82-99fd-e6159c0df489/air-max-97-shoe-EBZrb8.png'"
            ></v-img>
          </div>
          <div class="thumbnail mt-4 d-flex justify-center">
            <div class="mr-2 cursor-pointer" @click="changeImage(image)" v-for="(image, i) in images" :key="'image' + i">
              <v-img
                :class="showImage == image ? 'active' : ''"
                :aspect-ratio="1"
                width="70"
                :src="image"
              ></v-img>
            </div>
          </div>
        </v-col>
        <v-col md="4">
          <div class="filter-product-show">
            <div class="d-flex mb-3">
              <div class="number mr-2">01.</div>
              <div>
                <div class="label">GENDER</div>
                <div>
                  <v-chip-group>
                    <v-chip filter outlined label class="py-5 pr-5">
                      MEN
                    </v-chip>
                    <v-chip filter outlined label class="py-5 pr-5">
                      WOMEN
                    </v-chip>
                    <v-chip filter outlined label class="py-5 pr-5">
                      UNISEX
                    </v-chip>
                  </v-chip-group>
                </div>
              </div>
            </div>
            <div class="d-flex mb-3">
              <div class="number mr-2">02.</div>
              <div>
                <div class="label">STYLE</div>
                <div>
                  <v-chip-group>
                    <v-chip filter outlined label class="py-5 pr-5">
                      MEN
                    </v-chip>
                    <v-chip filter outlined label class="py-5 pr-5">
                      WOMEN
                    </v-chip>
                    <v-chip filter outlined label class="py-5 pr-5">
                      UNISEX
                    </v-chip>
                  </v-chip-group>
                </div>
              </div>
            </div>
            <div class="d-flex mb-3">
              <div class="number mr-2">03.</div>
              <div>
                <div class="label">COLOR</div>
                <div>
                  <v-chip-group style="flex-wrap: wrap;">
                    <v-chip
                      v-for="(color, i) in colors"
                      :key="'color' + i"
                      filter
                      outlined
                      label
                      class="py-5 pr-5"
                    >
                      <v-avatar
                        :style="
                          'border: 1px solid; background-color: ' + color.code
                        "
                        size="20"
                        class="mr-2"
                      >
                      </v-avatar>
                      {{ color.name }}
                    </v-chip>
                  </v-chip-group>
                </div>
              </div>
            </div>
            <div class="d-flex mb-3">
              <div class="number mr-2">04.</div>
              <div>
                <div class="label">SIZE</div>
                <div>
                  <v-chip-group column>
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
                </div>
              </div>
            </div>
            <div class="d-flex mt-6 box-price">
              <div class="number mr-2"></div>
              <div class="d-flex align-center" style="width: 100%;">
                <div class="price">
                  <span class="symbol">$</span>
                  30  
                </div>
                <div class="ml-7 box-btn">
                  <v-btn x-large color="black" class="white--text" block>Add to Cart</v-btn>
                </div>
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
    </section>

    <section class="mt-15">
      <v-row>
        <v-col cols="12" sm="8" md="9">
          <v-row>
            <v-col>
              <v-divider />
              <div class="title text-h6 font-weight-bold mt-3">CHECK THESE OUT TOO</div>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="6" sm="6" md="3" v-for="p in 8" :key="'product' + p">
              <product />
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="12" sm="4" md="3">
          <v-row>
            <v-col>
              <v-divider />
              <div class="title text-h6 font-weight-bold mt-3">DESCRIPTION</div>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
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
    sizes: [
      "3.5",
      "4",
      "4.5",
      "5",
      "5.5",
      "6",
      "6.5",
      "7",
      "7.5",
      "8",
      "8.5",
      "9",
      "9.5",
      "10",
      "10.5",
      "11",
      "11.5",
      "12",
      "12.5",
      "13",
      "13.5",
      "14",
      "15",
      "16",
      "17",
      "18",
    ],
    selectSize: [],
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
      'https://static.nike.com/a/images/t_PDP_1280_v1/f_auto,q_auto:eco/a47b2ef9-8239-4e82-99fd-e6159c0df489/air-max-97-shoe-EBZrb8.png',
      'https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5,q_80/oihgcfk3ykelvgmwwrqu/air-max-97-shoe-EBZrb8.png',
      'https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5,q_80/50cbf7c9-2a4a-41e5-a2ef-4b3acd7fa664/air-max-97-shoe-EBZrb8.png',
      'https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5,q_80/n3hfzt89anzujlouyrzy/air-max-97-shoe-EBZrb8.png'
    ],
    showImage: ''
  }),

  methods: {
    changeImage(img){
      this.showImage =img
    }
  }
};
</script>

<style lang="scss" scoped>
.thumbnail{
  .v-image{
    &.active{
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
  .box-price{
    margin-left: 17px;
    .price{
      width: 70px;
      font-size: 60px;
      font-weight: 500;
      padding-left: 17px;
      position: relative;
      line-height: normal;
      .symbol{
        position: absolute;
        font-size: 26px;
        top: 0;
        left: 0;
        font-weight: 300;
      }
    }
    .box-btn{
      width: 100%;
    }
  }
}
</style>