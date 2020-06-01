<template>
    <div>
        <header>
            <navbar>Hello</navbar>
        </header>

        <v-parallax src="https://lh3.googleusercontent.com/vjuwRtuG8mkE0awiDhHTBoBXcS4k8O4ngBIzB-yROXq9N3QG0vPDedIl7CsSocPyk6kfBq9K2ZWPBkKTPqsP9wzEzXJWp6XoEwG9jDC0rMNZ1DWymqDXxBLUv38vXNqeEf2D1RiDgqaIeI1QjgMmm0io6JWC3ui0SH7XkvoBNQObbACmhEsWJB251rqNgUvlbtY9b7GkXrKucqBrrAcEULpYGTUXlanJEcaEBoyyxh2UuRFGp3Fevve9DnTXtynSq5suXIa6JRBl3UteR1Ydt7AQTnahYOq1AbJQbUnlKCzQqXekGIA6B3mp9qobF1Uec_P75yqBO4SB3Zjw8_9Rru1wkDnyNUtOdWiPb6FomwdFmvT23kbeYcnQsY5Z8M00MdO6YsYFA3r9I0XNwuggFX7td-eQLhpPTrHUg-qd3Oh1mMLL8FU6gJcmrp9s6ovParMZJ_HQ-YPFuRY9xwRQKx7I_zSwGl1yE-N44NCyVoJXaXEYMN-nR0EiJlvFQ8Mt4Yjy5UksUVpqD1cpqPStRzGTD97-Ya-AeTOn7EgUv6TnVsCaoX3pdSQbAJLV9xxxiJe9liGr2FWZUvwj1tkQQ1plnDT3dN-Z6EPvlXLJW5pi4KfG9i0CelzBi8jwGeqCNVhE2zX0nxD4OofMJrLu9elIABHpc-RrosNGDjT1qd9yW3d1GxgUSidHowWV_xK9nu1g=s586-w586-h440-rw">
            <v-row align="center" justify="center">
                <v-col class="text-center" cols="12">
                    <h1 class = "display-3 font-weight-thin mx-auto">
                        Portfolio
                    </h1>
                    <h4 class="subheading">Things I build.</h4>
                </v-col>
            </v-row>
        </v-parallax>
        <v-divider></v-divider>
    </div>
</template>

<script>
import navbar from '~/components/navbar.vue';

export default {
    components: {
      navbar,
      album
    }
}
</script>