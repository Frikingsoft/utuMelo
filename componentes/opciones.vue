<template>
     <v-row justify="center" align="center" class="mt-8">
      <v-col cols="10" class="d-flex flex-wrap">
        <v-card class="mx-auto mb-8 borde" max-width="250" v-for="(foto,index) in lasFotos" :key="index" @mouseenter="animarFoto(index)" @mouseleave="foto.animar=false">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            height="200px"
           
          ></v-img>
          <v-card-title :class="{'izquierda':foto.animar}"> {{foto.nombre}} </v-card-title>
          <v-card-subtitle :class="{'izquierda':foto.animar}"> {{foto.texto}} </v-card-subtitle>
          <v-card-actions :class="{'izquierda':foto.animar}">
            <v-btn color="blue accent-1" text @click="verFoto(foto)"> Más Información </v-btn>

            <v-spacer></v-spacer>

            <v-btn icon @click="verFoto(foto)">
              <v-icon>{{
                foto.ver ? 'mdi-chevron-up' : 'mdi-chevron-down'
              }}</v-icon>
            </v-btn>
          </v-card-actions>
          <v-expand-transition>
            <div v-show="foto.ver">
              <v-divider></v-divider>

              <v-card-text>
               {{foto.ampliacion}}
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-col>
    </v-row>
</template>
<script>
export default {
    data(){
        return{
            show: false,
            lasFotos: [
        { nombre: 'Cursos',texto:"Puede ver todos los cursos y sus Programas",ampliacion:"En esta sección podrá acceder a los distintos cursos y a los materiales. Como así también a los programas correspondientes a cada uno",ver:false,animar:false},
        { nombre: 'Novedades',texto:"Puede ver todas las Novedades",ampliacion:"No se pierda ninguna de nuestras novedades, estaremos publicando todas las nuevas informaciones y actividades",ver:false,rotacion:0,animar:false},
        { nombre: 'Exámenes',texto:"Puede ver las fechas de los exámenes",ampliacion:"Regístrese y consulte la fecha de los exámenes, también podra visualizar exámenes anteriores",ver:false,rotacion:0,animar:false},
        { nombre: 'Contacto',texto:"Consulte por los teléfonos de contacto",ampliacion:"Administración - 4642 9133   Adscripción - 4642 2121 ,  También puede localizarnos en google maps",ver:false,rotacion:0,animar:false},
        { nombre: 'Créditos',texto:"Sección reservada para los créditos",ampliacion:"Esta sección esta reservada para los créditos de los desarrolladores y colaboradores de la página",ver:false,rotacion:0,animar:false},
        
      ],
        }
    },
    methods:{
      animarFoto(e){
        this.lasFotos[e].animar=true
      },
      verFoto(foto){
        foto.ver = !foto.ver

        // Scrollear automaticamente al final de la página.
        setTimeout(function () {
          window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' })
        }, 250)
      }
    }
}
</script>
<style scoped>

.fondo {
  background-color: brown;
}
.borde{
    border:3px double rgb(235, 235, 236);
    border-radius: 2%;
    overflow: hidden;
}
.borde:hover{
  border:3px double rgb(84, 142, 218);
  cursor:pointer;
}
.izquierda{
  animation: desdeIzquierda linear .3s;
}

@keyframes desdeIzquierda{
    from{
    transform: translateX(-100%);
  }
  to{
transform: translateX(0);
  }
}

</style>