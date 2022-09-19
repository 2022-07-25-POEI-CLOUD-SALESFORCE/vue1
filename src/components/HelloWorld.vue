<template>
  <div class="hello">
    <h1>{{ nom}} {{ prenom }}</h1>
    <h2 v-if="afficheVille">{{ ville }}</h2>
    <h2 v-show="afficheVille">{{ ville }}</h2>
    <p v-if="afficheDate">{{ dateJour }}</p>
    <p v-show="afficheDate">{{ dateJour }}</p>
    <!-- boucle d'affichage -->
    <span v-for="i in 10" :key="i">Nombre {{ i }}<br /></span>
    <!-- avec un tableau i pour l'élément du tableau, j pour l'indice -->
    <span v-for="(i, j) in [3, 1, 7, 10, 12]" :key="j">
      Valeur de i: {{ i }} ayant l'index {{ j }}<br />
    </span>
    <!-- une boucle ul/li avec le tableau dans "data"-->
    <ul>
      <li v-for="(i, j) in tableau" :key="j">{{ i }}</li>
    </ul>
  </div>
</template>

<script>
// https://github.com/2022-07-25-POEI-CLOUD-SALESFORCE/vue1.git
export default {
  name: 'HelloWorld',
  data() {
    return {
      nom: 'TAVERNIER',
      prenom: 'Bruno',
      ville: 'Montpellier',
      dateJour: new Date().toLocaleDateString(),
      afficheDate: true,
      afficheVille: true,
      tableau: ['lundi', 'mardi', 'mercredi', 'jeudi', 'vendredi', 'samedi', 'dimanche']
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-size: 3em; 
  text-shadow: 3px 3px 3px lime;
}
h2 {
  font-size: 2.5em;
  color: blue;
}
p {
  padding: 10px;
  border: 1px solid silver;
  box-shadow: 2px 2px 2px rgba(0,0,0,.4);
}
ul {
  list-style-type: none;
}
</style>
