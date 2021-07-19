// Future Interactive Version:
<template>
    <div bg>
        <header>
            <navbar></navbar>
        </header>

        <v-card class="ma-6 mx-10 rounded-lg" elevation="6">
            <v-row>
                <v-col md="9">
                    <v-card-title class="font-weight-medium name display-3">Elias Joaquín Little</v-card-title>
                    <v-card-subtitle class="blue--text text--darken-2 font-weight-bold subtitle-1 ml-1">Full-Time Student</v-card-subtitle>
                    <v-btn rounded v-for="Link in Links" :key="Link.title" class="ml-4" :to="Link.link"><v-icon left>{{Link.icon}}</v-icon>{{Link.title}}</v-btn>
                </v-col>
                <v-col md="3">
                    <v-avatar size="140" class="mr-6 float-right">
                        <img src="img/eliasHeadshot.jpg"/>
                    </v-avatar>
                </v-col>
            </v-row>
            <v-row md="7" class="ml-6 text-decoration-underline">
                <h1 class="font-weight-bold">Experience</h1>
            </v-row>
            <v-divider></v-divider>
            <v-row>
                <v-col md="7"  v-for="Ex in Experience" :key="Ex.title" >
                    <v-hover v-slot:default="{ hover }">
                        <v-card :elevation="hover ? 12 : 2" class="mx-4 transition-swing">
                            <v-card-title>{{Ex.title}}</v-card-title>
                            <v-card-subtitle class="font-weight-bold blue--text text--darken-2">{{Ex.subtitle}}</v-card-subtitle>
                            <v-expansion-panels v-model="panel">
                                <v-expansion-panel>
                                    <v-expansion-panel-header>{{Ex.summary}}</v-expansion-panel-header>
                                    <v-expansion-panel-content>
                                       {{Ex.description}}
                                    </v-expansion-panel-content>
                                </v-expansion-panel>
                            </v-expansion-panels>
                        </v-card>
                    </v-hover>
                </v-col>
            </v-row>

        </v-card>
    </div>
</template>
<script>
import navbar from '~/components/navbar.vue';

export default {
    components: {
        navbar
    },
    data: () => ({
      Links: [
        {
            'title':'LinkedIn',
            'icon':'mdi-linkedin',
            'link':'/#profiles'
        },
        {
            'title':'GitHub',
            'icon':'mdi-github',
            'link':'/#profiles'
        },
        {
            'title':'Website',
            'icon':'mdi-cloud',
            'link':'/'
        },
        {
            'title':'EliasJLittle@gmail.com',
            'icon':'mdi-email',
            'link':'/contact'
        },
        {
            'title':'(512)-788-4349',
            'icon':'mdi-phone',
            'link':'/contact'
            },
        {
            'title':'Austin, TX',
            'icon':'mdi-pin',
            'link':'www.google.com/maps/place/Austin,+TX/'
        }
      ],
      Experience: [
          {
              "title":"Intern",
              "subtitle":"Applied Research Labs",
              "date":"Summer 2019",
              "location":"Austin, TX",
              "summary":"Designed, built, tested, and presented a prototype low-cost low- frequency underwater acoustic source",
              "description":"Part of the J.J. Pickle Research Center, a part of UT Austin, ..."
          },
          {
              "title":"Contractor",
              "subtitle":"Torzal Guitars",
              "date":"Summer 2018-Current",
              "location":"Austin, TX",
              "summary":"Researched, designed, and constructed a small-scale Enterprise Re- source Planning database. Designed merchandise.",
              "description":""
          }
      ]
    })
}
</script>
<style scoped>
    .name {
        font-family: "Carlito";
    }
</style>
