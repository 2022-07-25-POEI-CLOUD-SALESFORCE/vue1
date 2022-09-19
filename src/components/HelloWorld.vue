<template>
  <div class="hello">
    <h1>{{ nom}} {{ prenom }}</h1>
    <h2 v-if="afficheVille">{{ ville }}</h2>
    <h2 v-show="afficheVille">{{ ville }}</h2>
    <p v-if="afficheDate">{{ dateJour }}</p>
    <p v-show="afficheDate">{{ dateJour }}</p>
    <p>
      <button @click="affDate">Afficher/Masquer la date</button>
      <button @click="afficheDate = !afficheDate">Afficher/Masquer la date</button>
    </p>
    <p>
      <button @click="count++">Vous avez cliqué {{ count }} fois</button>
    </p>
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
    <button v-on:click="alerte">Un bouton</button>
    <!-- séparation bouton gauche/droit de la souris + blocage menu contextuel -->
    <button @click.left="alerte" @click.right.prevent="alerte2">Cliquez moi</button>
    <!-- .once pour ne gérer qu'un seul clic -->
    <button @click.once="console">La console</button>
    <!-- .prevent pour bloquer le comporte normal du lien -->
    <a href="http://www.google.fr" target="_blank" @click.prevent="alerte">Lien</a>
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
      tableau: ['lundi', 'mardi', 'mercredi', 'jeudi', 'vendredi', 'samedi', 'dimanche'],
      count: 0
      //pour github, le répertoire node_modules n'est pas envoyé
      // il faut faire un npm install après récupération
    }
  },
  methods: {
    alerte() {
      alert('ok');
    },
    alerte2() {
      alert('droit');
    },
    console() {
      console.log('Yo !');
    },
    affDate() {
      this.afficheDate = !this.afficheDate;
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
