<template>
  <div>
    <v-card tile elevation="0">
      <v-chip outlined class="ma-2 card-tag" x-small v-if="tag"> {{ tag }} </v-chip>
      <router-link to="/show">
      <v-img
        :aspect-ratio="3/4"
        :src="image"
      ></v-img>
      </router-link>

      <div class="d-flex text mt-2 pa-2">
        <div class="text-left">
          <div class="color">{{ colorName }}</div>
          <div class="card-title">{{ title }}</div>
          <div class="price">${{ price }}</div>
        </div>
        <v-spacer></v-spacer>
        <div class="text-right">
          <div class="color">3 Colors</div>
          <div class="color-icon" v-if="$vuetify.breakpoint.smAndUp">
            <v-tooltip
              bottom
              v-for="(color, i) in colors"
              :key="color.name + i"
            >
              <template v-slot:activator="{ on, attrs }">
                <div
                  @click="colorName = color.name"
                  v-bind="attrs"
                  v-on="on"
                  class="cursor-pointer icon"
                  :style="'background: ' + color.code"
                ></div>
              </template>
              <span>{{ color.name }}</span>
            </v-tooltip>
          </div>
        </div>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  props: [
    'title',
    'price',
    'image',
    'tag'
  ],

  components: {
    //
  },

  data: () => ({
    colorName: 'Black',
    
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
    ],
  }),
};
</script>

<style lang="scss" scoped>
.v-card {
  position: relative;
  .card-tag {
    position: absolute;
    z-index: 1;
    left: 0;
    border: 1px solid rgba(0, 0, 0, 0.2);
    .v-chip__content {
      align-items: center;
      display: inline-flex;
      height: 100%;
      max-width: 100%;
      font-weight: 600;
    }
  }
  .text {
    .color {
      font-size: 8px;
      font-weight: 300;
    }
    .card-title {
      font-size: 12px;
      font-weight: 500;
    }
    .price {
      font-size: 12px;
      font-weight: 700;
    }
    .color-icon {
      display: flex;
      margin-top: 5px;
      justify-content: flex-end;
      .icon {
        cursor: pointer;
        width: 6px;
        height: 6px;
        margin-left: 2px;
        border-radius: 50%;
        border: 1px solid;
      }
    }
  }
}
</style>