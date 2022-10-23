<template>
    <div>
      <h1 class="text-subtitle-1 grey--text mt-1">Team</h1>
      <v-container class="my-4">
        <v-row>
          <v-col cols="12" xs="12" sm="6" md="4" lg="3"
          v-for="person in team" :key="person.name"
          >
            <v-card class="ma-3">
              <v-responsive class="text-center pt-4">
                <v-avatar size="100" class="grey lighten-2">
                  <img class="pa-1" :src="person.avatar">
                </v-avatar>
              </v-responsive>
              <v-card-text class="text-center">
                <div class="text-subtitle-1" v-text="person.name"></div>
                <div class="grey--text" v-text="person.role"></div>
              </v-card-text>
              <v-card-action>
                <v-btn text color="grey">
                  <v-icon small left>mdi-message</v-icon>
                  <span>Enviar Mensagem</span>
                </v-btn>
              </v-card-action>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>

<style>

</style>

<script>
export default {
  data: () => ({
    team:[
      {name:'Vinicius Augustus', role:'Dev FrontEnd', avatar:'/Vini.png'},
      {name:'Bulbassaoru', role:'Designer Gráfico', avatar:'/Bulbasaur.png'},
      {name:'Charmander', role:'Esquenta Café', avatar:'/Charmander.png'},
      {name:'Squirtle', role:'Dev Backend', avatar:'/squirtle.png'},
      {name:'Pikachu', role:'Marketing', avatar:'/Pikachu.png'},
    ]
  })
}
</script>