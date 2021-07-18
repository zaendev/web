<template>
  <v-footer dark padless class="mt-10">
    <v-card flat tile class="black lighten-1 white--text text-center">
      <v-card-text class="d-flex justify-center align-center my-5">
        <div class="text-h6 white--text mr-5">
          SIGN UP FOR OUR NEWSLETTER, GET 10% OFF YOUR NEXT ORDER
        </div>
        <div>
          <v-text-field
            dense
            hide-details
            outlined
            placeholder="discount@me.com"
            append-icon="mdi-email"
          ></v-text-field>
        </div>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet.
        Mauris cursus commodo interdum. Praesent ut risus eget metus luctus
        accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a
        sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula
        lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus
        iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor
        vel ut orci. Orci varius natoque penatibus et magnis dis parturient
        montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>---</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    //
  }),
};
</script>