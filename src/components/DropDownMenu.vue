<template>
    <div class="text-center">
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="grey"
            text
            v-bind="attrs"
            v-on="on"
          >
            <v-icon small left>mdi-chevron-down</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list>
          <v-list-item 
          v-for="link in links" :key="link.route"
          router :to="link.route">
            <v-list-item-title v-text="link.text"></v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
  </template>

<script>
export default{
    data: () =>({
        links:[
            {icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/'},
            {icon: 'mdi-folder', text: 'Meus Projetos', route: '/projects'},
            {icon: 'mdi-account', text: 'Equipe', route: '/team'},
        ]
    }),
}
</script>