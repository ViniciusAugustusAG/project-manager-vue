<template>
  <v-app id="app">
    <NavBar/>
    <v-content class="mx-4 mb-4">
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<style scoped>
#app{
  background-color: hsl(0, 0%, 92%);
}
</style>

<script>
import NavBar from "./components/NavBar.vue"
export default {
  name: "App",
  components:{
    NavBar,
  },

  data: () => ({
  }),
  methods:{
  }
};
</script>
