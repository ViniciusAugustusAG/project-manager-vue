<template>
  <div>
    <h1 class="text-subtitle-1 grey--text mt-1">Projects</h1>
    <v-container class="my-4">
      <v-expansion-panels>
        <v-expansion-panel v-for="project in myProjects" :key="project.title">
          
          <v-expansion-panel-header>
            {{project.title}}
            
            <template v-slot:actions>
              <v-icon color="primary">
                $expand
              </v-icon>
            </template>
          </v-expansion-panel-header>
          
          <v-expansion-panel-content class="px-4 grey--text">
            
            <div class="font-weight-bold">
              Prazo: {{project.due}}
            </div>

            <div
            v-text="project.content"
            ></div>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    projects:[
      {title:'Criar projeto Vue', person: 'Vinicius G.', due: '25 Out 2022', status: 'Em andamento', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Fazer design de app', person: 'Bulbasauro', due: '26 Out 2022', status: 'Concluido', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Programar a API', person: 'Charmander', due: '27 Out 2022', status: 'Em andamento', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Consertar bugs', person: 'Squirtle', due: '22 Out 2022', status: 'Atrasado', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Fazer o café', person: 'Pikachu', due: '29 Out 2022', status: 'Concluido', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
      {title:'Apresentar projeto Vue', person: 'Vinicius G.', due: '25 Out 2022', status: 'Em andamento', content:'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Rerum laborum illum cum corporis obcaecati, deleniti vitae minima iusto repellendus ipsa odit repellat. Reiciendis neque tempora nostrum omnis voluptatem sed harum!'},
    ]
  }),
  computed:{
    myProjects(){
      return this.projects.filter(project =>{
        return project.person == 'Vinicius G.'
      })
    },
  }
}
</script>

<style>

</style>