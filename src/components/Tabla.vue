<template>
    <v-data-table
    dense
    :headers="headers"
    :items="desserts"
    item-key="name"
    class="elevation-1"
  ></v-data-table>
</template>

<script>
    import productos from "./../assets/datos/productos.json"
    export default {
        data: () => ({
            productos,
      desserts: productos,
      headers: [
    
        { text: 'Nombre', value: 'nombre' },
        { text: 'Edad', value: 'edad' },
        { text: 'Fecha', value: 'fecha' },
        { text: 'Email', value: 'email' },
        
      ],
    }),
    }
</script>

<style lang="scss" scoped>

</style>