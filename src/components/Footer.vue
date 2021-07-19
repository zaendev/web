<template>
  <v-footer dark padless>
    <v-card flat tile class="black lighten-1 white--text text-center" width="100%">
      <v-card-text :class="{'d-flex justify-center align-center my-5': true, 'flex-column':($vuetify.breakpoint.smAndDown)}">
        <div :class="$vuetify.breakpoint.smAndDown ? 'text-h7 white--text mb-3' : 'text-h6 white--text mr-5'">
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

      <v-card-text class="white--text pt-0 text-left">
        <v-container>
          <v-row>
            <v-col md="3">
              <h4>ACCOUNT</h4>
              <ul class="menu-footer">
                <li>
                  <a href="#">My Account</a>
                </li>
                <li>
                  <a href="#">My Wishlist</a>
                </li>
                <li>
                  <a href="#">My Orders</a>
                </li>
              </ul>
            </v-col>
            <v-col md="3">
              <h4>ABOUT</h4>
              <ul class="menu-footer">
                <li>
                  <a href="#">About</a>
                </li>
                <li>
                  <a href="#">Term & Conditions</a>
                </li>
                <li>
                  <a href="#">Privacy Policy</a>
                </li>
                <li>
                  <a href="#">Contact Us</a>
                </li>
              </ul>
            </v-col>
            <v-col md="3">
              <h4>ABOUT</h4>
              <ul class="menu-footer">
                <li>
                  <a href="#">SHOP INFO</a>
                </li>
                <li>
                  <a href="#">Shipping Policies</a>
                </li>
                <li>
                  <a href="#">Return Policy</a>
                </li>
              </ul>
            </v-col>
            <v-col md="3">
              <v-img 
                alt="Logo" 
                class="shrink mr-2" 
                contain src="@/assets/logo-white.png"
                transition="scale-transition"
                width="100" />

              <div class="mt-3">
                <v-btn icon>
                  <v-icon color="white">mdi-facebook</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="white">mdi-instagram</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="white">mdi-youtube</v-icon>
                </v-btn>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        © {{ new Date().getFullYear() }} TUFT.
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

<style lang="scss" scoped>
  .menu-footer{
    margin-top: 10px;
    padding-left: 0;
    list-style: none;
    li{
      margin-top: 5px;
      margin-bottom: 5px;
      a{
        color: #fff;
        text-decoration: none;
        &:hover{
          text-decoration: underline;
        }
      }
    }
  }
</style>