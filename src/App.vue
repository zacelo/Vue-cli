<template>
  <div id="app">
    <div class="container mt-3 text-center">
      <div class="row">
        <div class="col-8">
          <ListaPersonas
            :propsEncabezado="encabezado"
            :propsListado="listado"
            titulo="Listado General"
          />
          <br />
          <ListaPersonas
            :propsEncabezado="encabezado"
            :propsListado=" filtrar('Femenino')"
            titulo="Listado Mujeres"
          />
          <br />
          <ListaPersonas
            :propsEncabezado="encabezado"
            :propsListado="filtrar('Masculino')"
            titulo="Listado Hombres"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ListaPersonas from "./components/ListaPersonas.vue";

export default {
  name: "App",
  components: {
    ListaPersonas,
  },
  data() {
    return {
      encabezado: ["id", "Nombre", "Edad", "Sexo"],
      listado: [
        {
          id: 1,
          nombre: "Marcelo",
          edad: 44,
          sexo: "Masculino",
        },
        {
          id: 2,
          nombre: "Carla",
          edad: 32,
          sexo: "Femenino",
        },
        {
          id: 3,
          nombre: "Juan",
          edad: 23,
          sexo: "Masculino",
        },
        {
          id: 4,
          nombre: "María",
          edad: 28,
          sexo: "Femenino",
        },
        {
          id: 5,
          nombre: "Sandra",
          edad: 46,
          sexo: "Femenino",
        },
        {
          id: 6,
          nombre: "Carlos",
          edad: 46,
          sexo: "Masculino",
        },
      ],
    };
  },
  methods: {
    filtrar(genero) {
      let listadoConFiltro = [];
      for (let i of this.listado) {
        if (i.sexo == genero) {
          listadoConFiltro.push(i);
        }
      }
      return listadoConFiltro;
    },
  },
};
</script>

<style>

</style>
