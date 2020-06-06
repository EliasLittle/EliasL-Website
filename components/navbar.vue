<template>
  <v-app-bar tile >
    <v-toolbar-title>Elias</v-toolbar-title>
    <v-divider inset vertical class="ml-4 mr-2"></v-divider>
    <v-btn text to="/" class="font-weight-light" nuxt>About Me</v-btn>
    
    <v-spacer></v-spacer>

    <v-btn text to="/involvements" class="font-weight-light" nuxt>Involvements</v-btn>
    <v-divider inset vertical class="mx-2"></v-divider>
    <v-btn text to="/portfolio" class="font-weight-light" nuxt>Portfolio</v-btn>
    <v-divider inset vertical class="mx-2"></v-divider>
    <v-btn text to="/blog" class="font-weight-light" nuxt>Stochastic Theories</v-btn>
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
