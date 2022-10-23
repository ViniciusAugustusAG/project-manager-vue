<template>
  <div>
    <h1 class="text-subtitle-1 grey--text mt-1">Dashboard</h1>
    <v-container class="my-4">  

      <v-row class="mb-3 ml-3">

        <v-btn 
        small text 
        color="grey" 
        @click="sortBy('title')"
        >
          <v-icon left small>mdi-folder</v-icon>
          <span class="text-caption text-lowercase">Nome do projeto</span>
        </v-btn>

        <v-btn 
        small text 
        color="grey" 
        @click="sortBy('person')"
        >
          <v-icon left small>mdi-account</v-icon>
          <span class="text-caption text-lowercase">Responsável</span>
        </v-btn>
      </v-row>

      <v-card
      v-for=" project in projects" :key="project.title" 
      :class="`pa-3 project ${project.status}`"
      >
        <v-row no-gutters>
          <v-col cols="12" xs="12" md="6">
            <div class="grey--text text-caption">Nome do projeto</div>
            <div v-text="project.title"></div>
          </v-col>

          <v-col cols="6" xs="6" sm="4" md="2">
            <div class="grey--text text-caption">Responsável</div>
            <div v-text="project.person"></div>
          </v-col>

          <v-col cols="6" xs="6" sm="4" md="2">
            <div class="grey--text text-caption">Data de entrega</div>
            <div v-text="project.due"></div>
          </v-col>

          <v-col cols="4" xs="2" sm="4" md="2">
            <div class="text-right">
              <v-chip small 
              v-text="project.status"
              :class="`${project.status} white--text text-caption my-2 mr-2`"
              ></v-chip>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>

<style scoped>
.project.Concluido{
  border-left: 5px solid #3cd1c2;
}
.project.Atrasado{
  border-left: 5px solid tomato;
}
.project.Em.andamento{
  border-left: 5px solid orange;
}

.v-chip.Concluido{
  background-color: #3cd1c2;
}
.v-chip.Atrasado{
  background-color: #f83e70;
}
.v-chip.Em.andamento{
  background-color: #ffaa2c;
}
  </style>

<script>
export default {
  data: () => ({
    projects:[
      {title:'Criar projeto vue', person: 'Vinicius G.', due: '25 Out 2022', status: 'Em andamento', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Fazer design de app', person: 'Bulbasauro', due: '26 Out 2022', status: 'Concluido', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Programar a API', person: 'Charmander', due: '27 Out 2022', status: 'Em andamento', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Consertar bugs', person: 'Squirtle', due: '22 Out 2022', status: 'Atrasado', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Fazer o café', person: 'Pikachu', due: '29 Out 2022', status: 'Concluido', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
    ]
  }),
  methods: {
    sortBy(par){
      this.projects.sort((a,b) => a[par] < b[par]? -1:1)
    }
  }
}
</script>
