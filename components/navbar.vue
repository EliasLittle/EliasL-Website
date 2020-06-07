<template>
  <v-app-bar tile >
    <v-toolbar-title>Elias</v-toolbar-title>
    <v-divider inset vertical class="ml-4 mr-2"></v-divider>
    <v-toolbar-items>
      <v-btn text to="/" class="font-weight-light" nuxt>About Me</v-btn>
    </v-toolbar-items>
    
    <v-spacer></v-spacer>

    <div class="hidden-md-and-up">
      <v-menu>
        <template v-slot:activator="{ on }">
          <v-icon v-on="on" large>mdi-menu</v-icon>
        </template>
        <v-list>
          <v-list-item v-for="item in menu" :key="item.title">
            <v-list-item-title><v-btn text :to="item.route" class="font-weight-light" nuxt>{{item.title}}</v-btn></v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>

    <v-toolbar-items class="hidden-sm-and-down" >
        <v-btn text v-for="item in menu" :key="item.title" :to="item.route" class="font-weight-light" nuxt>
          {{item.title}}
        </v-btn>
    </v-toolbar-items>

  </v-app-bar>
</template>
<script>
export default {
  data() {
    return {
      menu: [
        {
          "title":"Involvements",
          "route":"/involvements"
        },
        {
          "title":"Portfolio",
          "route":"/portfolio"
        },
        {
          "title":"Stochastic Theories",
          "route":"/blog"
        }
      ]
    }
  },
  methods: {}
}
</script>
<style scoped>
.header {
  margin-bottom: 0px;
}
</style>
