<template>
  <div class="image-text">
    <v-img
      :src="image"
      :aspect-ratio="ratio"
      class="grey darken-4"
      style="position: relative"
    >
      <div class="box-content pa-7">
        <div class="content">
          <div class="text">
            <h1 class="transition-swing text-h6 font-weight-bold white--text">
              {{ title }}
            </h1>
          </div>
          <v-btn large outlined color="white" class="mt-3" :to="link"> Shop Now </v-btn>
        </div>
      </div>
    </v-img>
  </div>
</template>

<script>
export default {
  props: [
    'ratio',
    'title',
    'link',
    'image'
  ],
  components: {
    //
  },
};
</script>

<style lang="scss" scoped>
.image-text {
  .box-content {
    height: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: start;
    .content {
      width: 400px;
    }
  }
}
</style>