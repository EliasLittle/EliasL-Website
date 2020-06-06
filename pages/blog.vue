<template>
    <div>
        <header>
            <navbar></navbar>
        </header>

        <v-parallax id="bg" src="">
            <v-row align="center" justify="center">
                <v-col class="text-center" cols="12">
                    <h1 class = "display-3 font-weight-thin mx-auto">
                        Stochastic Theories
                    </h1>
                    <h4 class="subheading">A collection of my random thoughts and theories.</h4>
                </v-col>
            </v-row>
        </v-parallax>
        <v-row align="center">
            <v-divider class="ma-6" dashed ></v-divider>
        </v-row>

        
    </div>
</template>

<script>
import navbar from '~/components/navbar.vue';
import involvements from '~/assets/json/involvements.json';

export default {
    components: {
      navbar
    },
    data() {
        return {
            Orgs : involvements
        }
    }
}
</script>

<style scoped>
    #bg {
        background-image:linear-gradient(.125turn,#6A4C93, #1982C4);
    }
</style>