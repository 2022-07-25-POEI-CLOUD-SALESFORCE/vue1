<template>
  <!-- pour lier un attribut HTML avec une variable JS on utilise 'v-bind:' ou la version courte ':' -->
  <!--<img v-bind:alt="msg" src="./assets/logo.png">
  <p :style="test">{{ msg }}</p>-->
  <HeaderComponent />
  <!--<RappelsComponent />-->
  <!--<MonComposant />
  <HelloWorld />-->
  <!-- pour retrouver les éléments plus facilement les éléments -->
  <!--<TabsComponent ref='tabs' id="tabs"/>
  <GalerieComponent ref='galerie' id="galerie" />-->
    <FormComponent />
    <ParentComponent />
  <FooterComponent />
</template>

<script>
  //pour utiliser un component il faut l'importer
//import HelloWorld from './components/HelloWorld.vue';
//import MonComposant from './components/MonComposant.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import FormComponent from './components/FormComponent.vue';
import ParentComponent from './components/ParentComponent.vue';
//import TabsComponent from './components/TabsComponent.vue';
//import GalerieComponent from './components/GalerieComponent.vue';
//import RappelsComponent from './components/RappelsComponent.vue';


export default {
  name: 'App',
  components: {
    // pour utiliser un component il faut le déclarer
    //  HelloWorld,
    //  MonComposant,
    HeaderComponent,
    FooterComponent,
    FormComponent,
    ParentComponent
},
  data() {
    return {
      msg: 'Hello M2I',
      test: {color: 'red'}
    }
  },
  /* hooks de création */
  beforeCreate() {
    console.log('before create');
  },
  created() {
    console.log('created');
  },
  /* hooks de compilation */
  beforeMount() {
    console.log('before mount');
  },
  mounted() {
    //le hook le plus utilisé, équivalent à $(document).ready() en JQUERY
    console.log('mounted');
    console.log(document.getElementById('tabs')); //élément avec id='tabs'
    console.log(this.$refs.tabs); //élément avec la ref='tabs'
    console.log(this.$refs); //liste de tous les éléments avec un attribut ref
  },
  /* hooks de mise à jour */
  beforeUpdate() {
    console.log('before update');
  },
  updated() {
    console.log('updated');
  },
  /* hooks de destruction */
  beforeUnmount() {
    console.log('before unmount');
  },
  unmounted(){
    console.log('unmounted');
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
