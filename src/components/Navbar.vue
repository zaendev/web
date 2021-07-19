<template>
    <div>
        <v-app-bar app color="white" class="px-0">
            <v-container v-if="$vuetify.breakpoint.mdAndUp" fluid class="d-flex align-center">
                <div class="d-flex align-center">
                    <router-link to="/">
                        <v-img alt="Vuetify Name" class="shrink" contain min-width="100"
                            src="@/assets/logo.png" width="100" />
                    </router-link>
                </div>

                <v-spacer></v-spacer>

                <v-btn text class="font-weight-bold">
                    About
                </v-btn>
                <v-menu open-on-hover offset-y rounded="0" elevation="0">
                    <template v-slot:activator="{ on, attrs }">
                        <v-btn
                            text
                            v-bind="attrs"
                            v-on="on"
                            to="/collections"
                             class="font-weight-bold">
                            Collections
                        </v-btn>
                    </template>
                    <v-card tile elevation="0" class="pt-5">
                        <v-container>
                            <v-row>
                                <v-col md="3" class="pa-1">
                                    <v-card tile elevation="0">
                                        <router-link to="/collections">
                                        <v-img
                                            :aspect-ratio="1"
                                            src="https://element9.solindo.com/img-tuft/Hair-Hair-Dryer_Below-Banner.jpg"
                                        ></v-img>
                                        </router-link>
                                        <div class="title ml-2">
                                            Summer 2021
                                        </div>
                                    </v-card>
                                </v-col>
                                <v-col md="3" class="pa-1">
                                    <v-card tile elevation="0">
                                        <router-link to="/collections">
                                        <v-img
                                            :aspect-ratio="1"
                                            src="https://element9.solindo.com/img-tuft/Hair-Iron-1-copy.jpg"
                                        ></v-img>
                                        </router-link>
                                        <div class="title ml-3">
                                            The Friday Projects
                                        </div>
                                    </v-card>
                                </v-col>
                                <v-col md="3" class="pa-1">
                                    <v-card tile elevation="0">
                                        <router-link to="/collections">
                                        <v-img
                                            :aspect-ratio="1"
                                            src="https://element9.solindo.com/img-tuft/Hair-Curler-3.jpg"
                                        ></v-img>
                                        </router-link>
                                        <div class="title ml-3">
                                            New Release
                                        </div>
                                    </v-card>
                                </v-col>
                                <v-col md="3" class="pa-1">
                                    <v-card tile elevation="0">
                                        <router-link to="/collections">
                                        <v-img
                                            :aspect-ratio="1"
                                            src="https://element9.solindo.com/img-tuft/Hair-Machine-4.jpg"
                                        ></v-img>
                                        </router-link>
                                        <div class="title ml-3">
                                            Best Sellers
                                        </div>
                                    </v-card>
                                </v-col>
                            </v-row>
                        </v-container>
                    </v-card>
                </v-menu>
                <v-btn text class="font-weight-bold">
                    Articles
                </v-btn>
                <v-btn text class="font-weight-bold">
                    Membership
                </v-btn>
                <v-btn text class="font-weight-bold">
                    Find A Store
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon>
                    <v-icon color="black">mdi-account</v-icon>
                </v-btn>
                <v-btn icon @click="openSearch = !openSearch">
                    <v-icon color="black"> mdi-magnify</v-icon>
                </v-btn>
                <v-btn icon>
                    <v-icon color="black">mdi-cart</v-icon>
                </v-btn>
            </v-container>
            <div v-if="$vuetify.breakpoint.smAndDown" fluid class="d-flex align-center w-100 px-0">
                <div class="d-flex align-center">
                    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
                </div>

                <v-spacer></v-spacer>
                <div>
                    <router-link to="/">
                        <v-img alt="Vuetify Logo" class="shrink mr-2" contain
                            src="https://tuftintl.com//image/catalog/tuft.png" transition="scale-transition"
                            width="100" />
                    </router-link>
                </div>
                <v-spacer></v-spacer>

                <v-btn icon v-if="$vuetify.breakpoint.smAndUp">
                    <v-icon color="black">mdi-account</v-icon>
                </v-btn>
                <v-btn icon v-if="$vuetify.breakpoint.smAndUp">
                    <v-icon color="black">mdi-magnify</v-icon>
                </v-btn>
                <v-btn icon>
                    <v-icon color="black">mdi-cart</v-icon>
                </v-btn>
            </div>
        </v-app-bar>

        <div class="box-search" v-if="openSearch">
            <v-text-field
            placeholder="Search"
            prepend-inner-icon="mdi-magnify"
            hide-details
          ></v-text-field>
        </div>

        <v-navigation-drawer v-if="$vuetify.breakpoint.smAndDown" v-model="drawer" absolute top temporary>
            <div class="pa-3">
                <v-text-field
                    dense
                    outlined
                    placeholder="Search"
                    prepend-inner-icon="mdi-magnify"
                    hide-details>
                </v-text-field>
            </div>

            <v-list nav dense>
                <v-list-item-group v-model="group" active-class="deep-purple--text text--accent-4">
                    <v-list-item @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">About</v-list-item-title>
                    </v-list-item>

                    <v-list-item to="/collections" @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">Collections</v-list-item-title>
                    </v-list-item>

                    <v-list-item @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">Articles</v-list-item-title>
                    </v-list-item>

                    <v-list-item @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">Membership</v-list-item-title>
                    </v-list-item>
                    <v-list-item @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">Find A Store</v-list-item-title>
                    </v-list-item>
                    <v-list-item @click.stop="drawer = false">
                        <v-list-item-title class="text-h6 font-weight-bold" style="line-height: 2rem;">Account</v-list-item-title>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script>

    export default {
        data: () => ({
            drawer: false,
            openSearch: false,
        }),

        watch: {
            drawer(){
                window.scrollTo({
                    top: 0,
                    left: 0,
                    behavior: 'smooth'
                });
            }
        }
    }
</script>

<style lang="scss" scoped>
    .box-search {
        position: fixed;
        top: 64px;
        background: #fff;
        width: 100%;
        z-index: 5;
        padding: 10px 30px;
        box-shadow: 0px 4px 5px 0px #0000002e;
    }
    .v-menu__content{
        min-width: 100%!important; 
        left: 0!important; 
        right: 0!important;
        box-shadow: -1px 3px 4px #0000002b;
    }
    .v-card {
        .title{
            font-size: 12px!important;
            font-weight: 500;
        }   
    }
</style>