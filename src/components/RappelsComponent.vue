<template>
  <div class="rappels">
    <!-- pour afficher une variable un utilise des doubles moustaches 
    v-bind: ou ':' permet de lier un attribut HTML avec une variable JS (par exemple le style)
    v-bind ou ':' permet aussi de lier des classes CSS avec des variables booléennes (vrai/faux)
    -->
    <h1 :style="monStyle" :class="{ maClasse: statut, maClasse2: !statut }">{{ msg }}</h1>
    <!-- v-on:click ou @click permet de lier l'évènement click avec une fonction (dans methods )-->
    <button @click="maFonction">Cliquez</button>
    <!-- structures répétitives (v-for) + attribut key obligatoire et unique -->
    <ul>
      <!-- i représente la valeur et j l'indice -->
      <li v-for="(i, j) in 10" :key="j">{{ j }} : {{ i }}</li>
    </ul>
    <ol>
      <li v-for="(val, cle) in [1,  3, 7, 8, 2, 5]" :key="cle">{{ cle }} : {{ val }}</li>
    </ol>

  </div>
</template>

<script>
  /* structure d'un fichier vue:
  - un template qui doit contenir un élément principal unique
  - un script avec une fonction exportée, qui contient au moins le nom du composant
  - du CSS (non obligatoire) qui peut être "scopé" pour ne pas déborder du composant */

  export default {
    name: 'RappelsComponent',
    //une fonction qui retourne des "datas" exploitables dans le script ou sur la page
    data() {
      return {
        //avant de l'afficher ou l'utiliser il faut déclarer les variables dans 'data'
        msg: 'Hello World !',
        monStyle: {textDecoration: 'underline', border: '1px solid silver'},
        statut: false
      }
    },
    // une partie pour mettre mes propres fonctions
    methods: {
      //fonction liée au clic sur le bouton
      maFonction() {
        //dans la classe, this fait référence à l'objet en cours d'utilisation
        this.msg = "Bonjour le Monde !";
        this.monStyle.textDecoration = 'overline';
        this.statut = true;
      }
    }
  }
</script>

<style scoped>
.maClasse {
  color: red;
}
.maClasse2 {
  color: blue;
}
</style>