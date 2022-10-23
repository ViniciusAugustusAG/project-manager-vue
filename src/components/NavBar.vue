<template>
    <div>
        <v-toolbar app flat id="nav-bar">
            <v-btn icon color="grey" @click="drawer = !drawer">
                <v-icon>mdi-menu</v-icon>
            </v-btn>
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Projeto</span>
                <span>Vue</span>
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <DropDownMenu/>

            <v-btn text color="grey">
                <span>Log Out</span>
                <v-icon right>mdi-logout</v-icon>
            </v-btn>
        </v-toolbar>

        <v-navigation-drawer 
        v-model="drawer" 
        temporary 
        width="300"
        overlay-color="primary"
        app class="primary"
        >

            <v-col>
                <v-row class="mt-5" justify="center">
                    <v-avatar size="100">
                        <img src="/Vini.png">
                    </v-avatar>
                </v-row>
                <v-row justify="center">                    
                    <p class="white--text text-subtitle-1 mt-1">Vinicius Augustus</p>
                </v-row>
                <v-row class="mt-4 mb-3" justify="center">
                    <PopUp/>
                </v-row>
            </v-col>

            <v-list>
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                    <v-list-item-action>
                        <v-list-item-icon>
                            <v-icon color="white" v-text="link.icon"></v-icon>
                        </v-list-item-icon>
                    </v-list-item-action>

                    <v-list-item-content>
                        <v-list-item-title class="white--text" v-text="link.text"></v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<style>
#nav-bar{
    background-color: hsl(0, 0%, 85%);
}
</style>

<script>
import DropDownMenu from './DropDownMenu.vue'
import PopUp from './PopUp.vue'
export default {
    components:{
        DropDownMenu,
        PopUp,
    },
    data: () =>({
        drawer: false,
        links:[
            {icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/'},
            {icon: 'mdi-folder', text: 'Meus Projetos', route: '/projects'},
            {icon: 'mdi-account', text: 'Equipe', route: '/team'},
        ]
    }),
    methods:{
    }
}
</script>
