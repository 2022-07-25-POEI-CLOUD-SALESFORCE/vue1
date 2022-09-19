<template>
  <!-- pour lier un attribut HTML avec une variable JS on utilise 'v-bind:' ou la version courte ':' -->
  <img v-bind:alt="msg" src="./assets/logo.png">
  <p :style="test">{{ msg }}</p>
  <MonComposant />
  <HelloWorld />
</template>

<script>
  //pour utiliser un component il faut l'importer
import HelloWorld from './components/HelloWorld.vue';
import MonComposant from './components/MonComposant.vue';


export default {
  name: 'App',
  components: {
    // pour utiliser un component il faut le déclarer
    HelloWorld,
    MonComposant
},
  data() {
    return {
      msg: 'Hello M2I',
      test: {color: 'red'}
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
