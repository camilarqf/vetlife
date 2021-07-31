<template>
  <v-app id="index">
    <v-app-bar app absolute color="#01b2ff" dark flat>
      <v-tabs right>
        <v-tab to="/">Home</v-tab>
        <v-tab to="/servico">Serviços</v-tab>
        <v-tab to="/contato">Contato</v-tab>
      </v-tabs>
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <Nuxt />
      </v-container>
      <v-btn
        v-scroll="onScroll"
        v-show="fab"
        fab
        dark
        fixed
        bottom
        right
        color="primary"
        @click="toTop"
      >
        <v-icon>mdi-chevron-up</v-icon>
      </v-btn>
      <v-col cols="12" lg="12" md="12" sm="12" class="ma-0 pa-0">
        <v-footer dark padless>
          <v-card class="flex" flat tile color="#01b2ff">
            <v-card-title class="justify-center" align-center>
              <strong
                class="subheading pa-2"
                :class="{
                  'text-h6': $vuetify.breakpoint.mdAndUp,
                  'subtitle-1': $vuetify.breakpoint.mdAndDown
                }"
                >Pós-Graduação UnyLeya, Desenvolvimento Front-end - BR / (60)
                99999-99999</strong
              >

              <v-spacer></v-spacer>

              <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
                <v-icon size="24px">
                  {{ icon }}
                </v-icon>
              </v-btn>
            </v-card-title>

            <v-card-text class="py-2 white--text text-center">
              <strong>VetLife</strong> — {{ new Date().getFullYear() }}
            </v-card-text>
          </v-card>
        </v-footer>
      </v-col>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    icons: ["mdi-facebook", "mdi-whatsapp", "mdi-instagram"],
    fab: false
  }),
  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 20;
    },
    toTop() {
      this.$vuetify.goTo(0);
    }
  }
};
</script>

<style scoped>
.v-application .mt-12 {
  margin-top: 78px !important;
}
a:-webkit-any-link {
  text-decoration: none;
}
</style>
