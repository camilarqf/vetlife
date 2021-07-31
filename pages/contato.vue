<template>
  <v-row justify="center" align="center" wrap>
    <v-col cols="12" lg="6" md="6" sm="8" class="mt-16 pb-16 mb-16">
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
