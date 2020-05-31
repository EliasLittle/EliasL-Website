<template>
    <div>
    <v-list-item>
        <v-list-item-content>
            <v-list-item-title><a class="black--text" href={{url}}>{{title}}</a></v-list-item-title>
            <v-list-item-subtitle>{{artist}}</v-list-item-subtitle>
            <!--<iframe src="https://open.spotify.com/embed/album/4SxFsOO0h4Nz3lFJuysKq5" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>-->
        </v-list-item-content>
    </v-list-item>
    <v-list-item>
          <v-list-item-content>
              {{embed}}
          </v-list-item-content>
    </v-list-item>
    </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {},
  props: {url,title,artist,embed}
}
</script>
