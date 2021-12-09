<template>
  <v-app>
   <v-app-bar app color="green" dark>
    <h1>Formulario</h1>
   </v-app-bar>

   <v-container>
   <Formulario/>
   <Tabla/>
   </v-container>

  </v-app>
</template>

<script>
import Formulario from "./components/Formulario.vue"
import Tabla from "./components/Tabla.vue"
  export default {
    components:{
      Formulario,
      Tabla
    }
    
  }
</script>

<style lang="scss" scoped>

</style>