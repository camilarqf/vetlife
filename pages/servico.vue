<template>
  <v-row justify="center" align="center" wrap>
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
          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/veterinary.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Clínica 24h
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              Atendimentos de rotina, urgências e emergências veterinárias 24
              horas com um corpo médico veterinário em constante
              plantão.Consultas, exames, procedimentos cirúrgicos e internação,
              a estrutura necessária para que nossos profissionais possam
              atender sempre com muito carinho.
            </v-card-text>
          </v-col>
          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/pet-shop.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Pet Shop
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              Camas, casas, brinquedos, acessórios para segurança e higiene,
              rações, petiscos, roupas. Uma seleção de produtos para cães e
              gatos com tudo que você precisa
            </v-card-text>
          </v-col>
          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/medicine.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Farmácia
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              Contamos com farmácia completa. Trazendo praticidade e
              conveniência para o tutor que precisar medicar seu pet, sempre com
              produtos das marcas mais confiáveis do mercado.
            </v-card-text>
          </v-col>

          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/grooming.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Banho e Tosa
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              Salão de banho e tosa amplo, monitoramento por câmeras,
              climatização com sistema de musicalização, toalhas individuais e
              esterilizadas, junto da maior e mais completa linha de cosméticos
              do mercado.
            </v-card-text>
          </v-col>
          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/test.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              Laboratório
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              O nosso laboratório conta com ótimos profissionais e com o que
              existe de mais moderno para o diagnóstico na medicina veterinária.
              Nossa infraestrutura, equipamentos sempre atualizados e
              atendimento diferenciado, garantem aos nossos clientes resultados
              rápidos e confiáveis.
            </v-card-text>
          </v-col>
          <v-col lg="4" md="4" sm="6" class="pa-16" align="center">
            <v-img
              class="mb-6"
              :src="require('~/assets/imagens/cardiogram.png')"
              width="150px"
              height="150px"
            ></v-img>

            <v-card-title class="d-block  blue--text">
              UTI Animal
            </v-card-title>
            <v-card-text class="blue--text text-subtitle-1 pa-2" align="left">
              O VetLife conta com uma Unidade de Terapia Intensiva completa, com
              capacidade para cuidar dos casos graves e de pacientes que
              demandam de suporte avançado à vida e monitorização contínua e de
              alto grau de complexidade.
            </v-card-text>
          </v-col>
        </v-row>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Arima+Madurai:wght@300;400&display=swap");
.titulo {
  font-family: "Arima Madurai", cursive;
}
</style>
