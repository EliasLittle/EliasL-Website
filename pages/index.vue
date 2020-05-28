<template>
    
  <div>
    
    <header>
      <navbar></navbar>
    </header>

    <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg">
        <div class = "display-4 font-italic font-weight-light mx-auto">
            Elias Joaquín Little
        </div>
    </v-parallax>

    <v-row>
        <v-col sm="12" lg="3">
            <v-container class=".d-md-none .d-lg-flex">
                <v-image src="img/eliasHeadshot.jpg"/>
            </v-container>
        </v-col>

        <v-col sm="12" lg="9">
            <about-me></about-me>
            <!--
            <v-container>
                <nuxt-content :document="aboutMe" />
            </v-container>
            -->
        </v-col>
    </v-row>
  </div>
</template>

<script>
import navbar from '~/components/navbar.vue';

export default {
    components: {
      navbar
    },
    async asyncData({$content}) {
        const aboutMe = await $content('AboutMe').fetch();
        return {aboutMe};
    }
}
</script>
