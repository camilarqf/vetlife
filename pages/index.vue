<template>
  <v-row justify="center" align="center" wrap>
    <v-col cols="12" class="pa-0 ma-0">
      <v-card
        fluid
        class="card rounded-b-xl "
        justify-center
        flat
        color="#01b2ff"
        align="center"
      >
        <v-img
          width="270"
          height="270"
          :aspect-ratio="16 / 9"
          :src="require('~/assets/imagens/imagem_home.png')"
        >
        </v-img>
        <v-card-text
          class=" white--text font-weight-bold"
          :class="{
            'text-h4': $vuetify.breakpoint.smAndUp,
            'subtitle-1': $vuetify.breakpoint.smAndDown
          }"
        >
          O maior e mais completo <br />HOSPITAL VETERINÁRIO
        </v-card-text>
        <div class="text-center">
          <v-btn to="/contato" rounded color="white blue--text" dark large>
            Entre em contato
          </v-btn>
        </div>
      </v-card>
    </v-col>
    <v-col cols="12" lg="6" md="6" sm="12">
      <v-card flat class="sec-1 rounded-lg mt-12 mb-12" align="center">
        <embed :src="require('~/assets/video.mp4')" width="80%" height="344" />
      </v-card>
    </v-col>
    <v-col cols="12" lg="6" md="6" sm="12">
      <v-card-text class=" blue--text " align="center">
        <h1 class="mb-6 titulo font-weight-bold">Bem-vindo ao VetLife</h1>
        <p class="text-body-1">
          O mais completo Hospital Veterinário da região Centro-oeste. Planejado
          para oferecer o conforto e excelência no atendimento que você e o seu
          pet merecem. Contamos com o mais experiente corpo clínico em diversas
          especialidades e ampla estrutura hospitalar de última geração.
        </p>
      </v-card-text>
    </v-col>
    <v-col cols="12 " class="ma-0 pa-0">
      <div
        fluid
        class="section-2 "
        :width="$vuetify.breakpoint.smAndUp ? 500 : 650"
      >
        <v-row justify="center">
          <h1 class="titulo font-weight-bold blue--text mt-12">
            Nossos Serviços
          </h1>
        </v-row>
        <v-row justify="center">
          <v-col lg="3" md="3" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/veterinary.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Clínica 24h
            </v-card-title>
          </v-col>
          <v-col lg="3" md="3" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/pet-shop.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Pet Shop
            </v-card-title>
          </v-col>
          <v-col lg="3" md="3" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/medicine.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Farmácia
            </v-card-title>
          </v-col>

          <v-col lg="3" md="3" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/grooming.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Banho e Tosa
            </v-card-title>
          </v-col>
        </v-row>
        <v-row justify="center">
          <div class="text-center mb-9">
            <v-btn to="/servico" rounded color=" white--text blue" dark large>
              Mais Informações
            </v-btn>
          </div>
        </v-row>
      </div>
    </v-col>
    <v-col cols="12" lg="6" md="6" sm="8" class="mt-16 mb-12">
      <v-card class="pa-4" elevation="6">
        <h1 align="center" class=" titulo blue--text mb-8">
          Contato
        </h1>
        <form>
          <v-row class="mb-12">
            <v-col cols="12" lg="6" md="6" sm="12">
              <v-text-field
                v-model="nome"
                :error-messages="nomeErrors"
                :counter="100"
                label="nome"
                required
                @input="$v.nome.$touch()"
                @blur="$v.nome.$touch()"
              ></v-text-field>
            </v-col>
            <v-col cols="12" lg="6" md="6" sm="12">
              <v-text-field
                v-model="email"
                :error-messages="emailErrors"
                label="E-mail"
                required
                @input="$v.email.$touch()"
                @blur="$v.email.$touch()"
              ></v-text-field>
            </v-col>
          </v-row>

          <v-textarea height="50" counter label="Mensagem"></v-textarea>
          <div class="text-center">
            <v-btn
              class="mr-4 pa-4"
              color="blue white--text"
              rounded
              @click="submit"
            >
              Enviar
            </v-btn>
          </div>
        </form>
      </v-card>
    </v-col>
    <v-card
      fluid
      class="card2 rounded-t-xl "
      justify-center
      flat
      color="#01b2ff"
      align="center"
    >
    </v-card>
  </v-row>
</template>

<script>
import { validationMixin } from "vuelidate";
import { required, maxLength, email } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],

  validations: {
    nome: { required, maxLength: maxLength(100) },
    email: { required, email }
  },

  data: () => ({
    nome: "",
    email: ""
  }),

  computed: {
    nomeErrors() {
      const errors = [];
      if (!this.$v.nome.$dirty) return errors;
      !this.$v.nome.maxLength &&
        errors.push("nome must be at most 10 characters long");
      !this.$v.nome.required && errors.push("nome is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    }
  },

  methods: {
    submit() {
      this.$v.$touch();
    }
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Arima+Madurai:wght@300;400&display=swap");

.card {
  height: 450px;
  background-color: #01b2ff;
  width: 100%;
}

.card2 {
  height: 50px;
  background-color: #01b2ff;
  width: 100%;
}
.v-application .rounded-b-xl {
  border-bottom-left-radius: 65px !important;
  border-bottom-right-radius: 65px !important;
}

.v-application .rounded-t-xl {
  border-top-left-radius: 65px !important;
  border-top-right-radius: 65px !important;
}
.v-application .subtitle-1 {
  line-height: 2rem;
}

.titulo {
  font-family: "Arima Madurai", cursive;
}

.section-2 {
  background-color: #f4fcff;
  width: 100%;
}
</style>
