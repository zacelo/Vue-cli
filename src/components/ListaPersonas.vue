<template>
  <div>
     <h1>{{titulo}}</h1>
    <table class="table">
      <thead class="bg-warning">
        
        <tr>
          <th scope="col" v-for="item in propsEncabezado" :key="item.id">
            {{ item }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="itemList in propsListado"
          :key="itemList.id"
          :class="itemList.sexo"         
        >   
          <td>{{ itemList.id }}</td>
          <td>{{ itemList.nombre }}</td>
          <td>{{ itemList.edad }}</td>
          <td>{{ itemList.sexo }}</td>    
          
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "ListaPersonas",
  props: {
    propsEncabezado: {
      type: Array,
    },
    propsListado: {
      type: Array,
    },
    titulo: {
      type: String,
    },
  },
};
</script>

<style lang="css" scoped>
.Femenino {
  background-color: rgba(240, 190, 245, 0.363);
}
.Masculino {
  background-color: rgb(166, 204, 255);
}
</style>