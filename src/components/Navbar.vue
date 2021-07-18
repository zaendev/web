<template>
    <v-app-bar app color="white" class="px-0">
        <v-container fluid class="d-flex align-center">
            <div class="d-flex align-center">
                <v-img alt="Vuetify Logo" class="shrink mr-2" contain
                    src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png" transition="scale-transition"
                    width="40" />

                <v-img alt="Vuetify Name" class="shrink mt-1 hidden-sm-and-down" contain min-width="100"
                    src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png" width="100" />
            </div>

            <v-spacer></v-spacer>

            <v-btn text>
                Shop
            </v-btn>
            <v-btn text to="/collections">
                Collections
            </v-btn>
            <v-btn text>
                Blog
            </v-btn>
            <v-btn text>
                Membership
            </v-btn>
            <v-btn text>
                Brand
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn icon>
                <v-icon color="black">mdi-account</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon color="black">mdi-magnify</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon color="black">mdi-cart</v-icon>
            </v-btn>
        </v-container>
    </v-app-bar>
</template>

<script>

    export default {
        data: () => ({
            //
        })
    }
</script>