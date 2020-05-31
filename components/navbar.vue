<template>
  <v-app-bar tile >
    <v-toolbar-title><nuxt-link class="black--text headline" to="/">Elias</nuxt-link></v-toolbar-title>
    
    <v-spacer></v-spacer>

    <v-btn text> Groups</v-btn>
    <v-btn text><nuxt-link class="black--text" to="/portfolio">Portfolio</nuxt-link></v-btn>
    <v-btn text><nuxt-link class="black--text" to="/blog">Blog</nuxt-link></v-btn>
  </v-app-bar>
</template>
<script>
export default {
  data() {
    return {}
  },
  methods: {}
}
</script>
<style scoped>
.header {
  margin-bottom: 0px;
}
</style>
