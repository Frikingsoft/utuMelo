<template>
  <v-row justify="center" align="center" class="mt-12">
    <v-col cols="5">
      <v-carousel v-model="seleccion" height="350">
        <v-carousel-item v-for="(foto, index) in fotos" :key="index">
          <v-sheet color="primary" height="100%" tile>
            <v-row class="fill-height" align="center" justify="center">
              <v-img :aspect-ratio="16/9" :src="`${foto.url}`"> </v-img>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </v-row>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      seleccion: 0,
      fotos: [
        {
          url:
            "https://pbs.twimg.com/media/EesD7NMWAAUA1Bo.jpg",
        },
        {
          url:"https://www.lagomerin.com.uy/images/utu-melo.jpg"
        },
        {
          url:"https://i2.wp.com/atlasdiario.com.uy/wp-content/uploads/2019/08/04-210819A.jpg?fit=820%2C580&ssl=1"
        }
      ],
    }
  },
}
</script>
