<template>
  <div>
    <h1>leoanrdo</h1>

    <v-form  ref="productos" v-model="valid">
      <v-container>
        <v-row>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="nombreText"
              :rules="nameRules"
              :counter="10"
              label="Nombre"
              
              
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="edadText"
              
              :counter="10"
              label="edad"
              type="number"
             
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="fechaText"
              type="date"
              :counter="10"
              label="Fecha"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="emailText"
              :rules="emailRules"
              label="E-mail"
              required
            ></v-text-field>
          </v-col>
        </v-row>
      </v-container>
      <v-btn @click="enviarDatos()">Enviar</v-btn>
    </v-form>
  </div>
</template>

<script>
import productos from "./../assets/datos/productos.json"
export default {
  data: () => ({
      productos,
    valid: false,
    nombreText: "",
    edadText:"",
    fechaText: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 10 || "Name must be less than 10 characters",
    ],
    emailText: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
    datos:{}
  }),
  methods:{
        enviarDatos(){
           this.$refs.productos.validate()
             const datoAgregar = {
               nombre:this.nombreText,
               edad:this.edadText,
               fecha:this.fechaText,
               email:this.emailText
                }
               this.productos.push(datoAgregar);

               this.nombreText="",
               this.edadText="",
               this.fechaText="",
               this.nombreText="",
               this.emailText=""

                
        }
  }
};
</script>

<style lang="scss" scoped></style>
