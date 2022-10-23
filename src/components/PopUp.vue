<template>
<div class="text-center">
    <v-dialog
      v-model="dialog"
      width="600"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="success"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Criar novo projeto
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey--text text--darken-2">
          Criar novo projeto
        </v-card-title>

        <v-card-text>
          <v-form class="px-3" ref="form">
            <v-text-field
            label="Título"
            v-model="title"
            prepend-icon="mdi-folder"
            :rules="inputRules"
            ></v-text-field>

            <v-textarea
            label="Informação"
            v-model="content"
            prepend-icon="mdi-pencil"
            :rules="inputRules"
            ></v-textarea>

            <v-menu>
                <template v-slot:activator="{on, attrs}">
                    <v-text-field 
                    v-on="on"
                    v-bind="attrs"
                    label="Data de entrega"
                    prepend-icon="mdi-calendar-range"
                    :value="formattedDate"
                    :rules="inputRules"
                    class="date-menu"
                    ></v-text-field>
                </template>
                <v-date-picker v-model="due"></v-date-picker>
            </v-menu>

          </v-form>

          <v-card-actions>
            <v-row>
                <v-col>
                    <v-btn 
                    class="success nx-0 mt-3"
                    @click="submit()"
                    >
                        Adicionar Projeto
                    </v-btn>
                </v-col>
                <v-col cols="3">
                    <v-btn 
                    text color="grey"
                    class="nx-0 mt-3"
                    @click="dialog = false"
                    >
                    Cancelar
                    </v-btn>
                </v-col>
                <v-spacer></v-spacer>
            </v-row>
          </v-card-actions>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>

<style>
.date-menu{
    width: 50%;
}
</style>

<script>
import moment from 'moment'
export default {
    data:() => ({
        dialog: false,
        title:'',
        content:'',
        due: null,
        inputRules:[
            v => v.length >= 3 || 'Tamanho mínimo de 3 caracteres'
        ],

    }),
    methods:{
        submit(){
            if (this.$refs.form.validate()){
                console.log(this.title, this.content, this.formattedDate)
            }
        }
    },
    computed: {
    formattedDate() {
      return this.due ? moment(this.due).format("DD/MM/YYYY") : "";
    }
    } 
}
</script>
