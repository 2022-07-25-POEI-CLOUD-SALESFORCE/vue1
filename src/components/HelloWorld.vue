<template>
  <div class="hello">
    <h1>{{ nom}} {{ prenom }}</h1>
    <h2 v-if="afficheVille">{{ ville }}</h2>
    <h2 v-show="afficheVille">{{ ville }}</h2>
    <p v-if="afficheDate">{{ dateJour }}</p>
    <p v-show="afficheDate">{{ dateJour }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      nom: 'TAVERNIER',
      prenom: 'Bruno',
      ville: 'Montpellier',
      dateJour: new Date().toLocaleDateString(),
      afficheDate: true,
      afficheVille: true
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
</style>
