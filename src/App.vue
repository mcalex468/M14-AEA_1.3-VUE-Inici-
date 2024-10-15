<script setup>
import { ref, reactive } from 'vue';

// Definimos una variable reactiva
const contador = ref(0);
const usuari = reactive({  // Si hablamos de objetos se debe usar reactive, no ref
  nom: 'alex',
  edat: 19
});

// Función que modifica el valor
const incrementar = () => {
  contador.value++;
};

const aumentarEdat = () => {
  usuari.edat++;
};

// Exemple v.bind Variable para la URL de la imagen
const imatgeURL = "https://s3.amazonaws.com/cdn.wp.m4ecmx/wp-content/uploads/2023/10/14123804/ias-generadoras-de-imagenes.jpg";

const titol = "Hola texto prueba";

// Exemple v-model
const nomUsuari = ref('');  // variable que no es array o objecte => sempre Ref()


// Directiva v-for
const productos = [ 
{  id: 1,  nombre: "Costillas",  preu: "55" },
{id: 1, nombre: "Pollo", preu: "35"},
{id: 1, nombre: "Alitas", preu: "25" },
{id: 1, nombre: "Cordero", preu: "45" }
] 

// Ejemplo if
const logat = ref(false);
 

// Ejemplo v-show
const mostrar = ref('');

</script>

<template>
  <div>
    <h2>Variable Reactiva</h2>
    <p>El contador és: {{ contador }}</p> 
    <button @click="incrementar">Incrementar</button>
  </div>

  <div>
    <h2>Objeto Reactivo</h2>
    <p>Nom: {{ usuari.nom }}</p>
    <p>Edat: {{ usuari.edat }}</p>  
    <button @click="aumentarEdat">Incrementar Edat</button>
  </div>

  <div>
    <h2> Directiva V-bind</h2>
    <h1 v-bind:title="titol">Pasa el ratón por encima</h1>  
    <img :src="imatgeURL" alt="Imatge"> 
  </div>

  <div>
    <h2>Directiva V-Model</h2>
    <p> Nom Usuari: {{ nomUsuari }}</p>
    <input type="text" placeholder="Escribe tu nombre porfavor" v-model="nomUsuari">
  </div>

  <div>
    <h1>Directiva V-For</h1>
    <ul>
      <li v-for="producto in productos" :key="producto.id"> {{ producto.nombre }} - {{ producto.preu }}</li>
    </ul>
  </div>

  <div>
    <h2>Directiva V-if</h2>
    <p v-if="logat">Benvingut Usuari</p>
    <p v-else>No estas logat. Si us plau Inicia Sesio</p>
  </div>

  <div>
    <h2>Directiva V-Show</h2>
    <button @click="mostrar =! mostrar">Alternar Visibilitat</button>
    <p v-show="mostrar">Texto visible</p>
  
  </div>
</template>



<style scoped>
body {
  display: flex;
  flex-direction: column;
}


header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
