<template>
  <v-app class="fondo">
    <v-app-bar app class="banner">
      <v-container>
        <v-row>
          <v-col cols="2">
            <div class="d-flex align-center">
              <v-btn
                fab
                outlined
                color="white"
                max-width="50px"
                max-height="50px"
                @click="abrirMenu = !abrirMenu"
               style="border:solid 2px"
               class="d-flex align-center"
              >
             <v-icon  x-large color="white">mdi-menu</v-icon>
              </v-btn>
            </div>
          </v-col>
          <v-col cols="8" class="d-flex justify-center align-center titulo">
           <h3> Escuela Superior de Melo</h3>
            <v-icon dark large class="ml-4">mdi-school</v-icon>
          </v-col>
          <v-col cols="2" class="d-flex justify-center align-center">
            <input type="text" class="textoIngresado">
            <input type="button" class="botonLlave" @click="registro">
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>
    <v-navigation-drawer app v-model="abrirMenu" absolute temporary class="banner">
      <elmenu></elmenu>
    </v-navigation-drawer>
    <v-container>
      <nuxt />
    </v-container>
     <v-footer
      app
      class="d-flex align-center justify-center banner"
    >
    <h3 class="titulo">{{elmensaje}}</h3>
    </v-footer>
  </v-app>
</template>

<script>
import elmenu from '../componentes/elmenu'
export default {
  components:{
    elmenu
  },
  data() {
    return {
      abrirMenu:false,
      elmensaje:'Tu futuro comienza en UTU ©'
    }
  },
  methods:{
    registro(){
      this.$router.push('/registro')
    }
  }
}
</script>
<style scoped>
@import url('../estilos/default/default.css');
</style>