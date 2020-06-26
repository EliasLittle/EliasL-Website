<template>
    <!-- hobby cards -->
    <v-row style="background:#F5F5F5" class="mx-n10 px-5 py-2">
        <!-- Albums Card -->
        <v-col sm="12" lg="4" class="">
            <v-card outlined class="mx-auto">

                <v-list-item-content class="mx-2">
                    <div class="overline mb-4">Ears</div>
                    <v-list-item-title class="headline mb-1">Music</v-list-item-title>
                    <v-list-item-subtitle>Some of my favorite albums</v-list-item-subtitle>
                </v-list-item-content>

                
                <v-list two-line shaped>

                    <v-list-group 
                    v-for="album in AlbumList" 
                    :key="album.title"
                    multiple 
                    no-action
                    active-class="blue--text">
                        <template v-slot:activator>
                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title>{{album.title}}</v-list-item-title>
                                    <v-list-item-subtitle>{{album.artist}}</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>
                        </template>
                        <v-list-item>
                            <v-list-item-content>
                                <iframe :src="album.embed" width="300" height="380" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
                            </v-list-item-content>
                        </v-list-item>
                    </v-list-group>

                </v-list>

            </v-card>
        </v-col>
        <!-- Books Card -->
        <v-col sm="12" lg="4" class="">
            <v-card outlined class="mx-auto">
                <v-list-item-content class="mx-2">
                    <div class="overline mb-4">Eyes</div>
                    <v-list-item-title class="headline mb-1">Reading List</v-list-item-title>
                    <v-list-item-subtitle>Books I'm currently reading or have recently read</v-list-item-subtitle>
                </v-list-item-content>

                <v-list two-line shaped>

                    <v-list-group 
                    v-for="book in BookList" 
                    :key="book.title"
                    multiple 
                    no-action
                    active-class="blue--text">
                        <template v-slot:activator>
                            <v-list-item>
                                <v-list-item-content>
                                    <v-list-item-title>{{book.title}}</v-list-item-title>
                                    <v-list-item-subtitle class="text--primary d-none d-md-flex d-lg-none">{{book.subtitle}}</v-list-item-subtitle>
                                    <v-list-item-subtitle >{{book.author}}</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>
                        </template>
                        <v-list-item>
                            <v-list-item-content>
                                <v-row>
                                    <v-col sm="3" lg="6" class="mx-2">
                                        <a target="_blank" :href="book.urlone"><img border="0" :src="book.urltwo" ></a><img src="book.urlthree" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
                                    </v-col>
                                    <!-- Future addition: Review link
                                    <v-col sm="8" md="4" lg="6" class="mx-2">
                                        <v-sheet color="blue lighten-3" height="250" class="float-right d-lg-flex">{{book.review}}</v-sheet>
                                    </v-col>
                                    -->
                                </v-row>
                            </v-list-item-content>
                        </v-list-item>
                    </v-list-group>

                </v-list>

            </v-card>
        </v-col>

        <!-- Thoughts Card -->
        <v-col sm="12" lg="4" class="">
            <v-card outlined class="mx-auto">
                <v-list-item-content class="mx-2">
                    <div class="overline mb-4">Mind</div>
                    <v-list-item-title class="headline mb-1">Some Thoughts</v-list-item-title>
                    <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
                </v-list-item-content>
            </v-card>
        </v-col>
    </v-row>
</template>
<script>
import albumlist from '~/assets/json/albums.json';
import booklist from '~/assets/json/books.json';

export default {
  data() {
    return {
        AlbumList: albumlist,
        BookList: booklist,
    }
  },
  methods: {}
}
</script>