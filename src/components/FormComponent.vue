<template>
  <div class="form">
    <form @submit.prevent="traitement"> 
      <div>
        <label>Nom</label>
        <!-- v-model : liaison bi-directionnelle html<->JS 
             v-model.lazy : mise à jour sur le blur plutot que sur le change 
             v-model.trim : suppression des espaces avant et après le texte
             v-model.number : nombre uniquement
        -->
        <input v-model="nom" placeholder="votre nom ici" :class='{ko: nomKo}' />
        <p v-show="nomKo" class="ko">Votre nom doit comporter au moins 2 caractères...</p>
      </div>
      <div>
        <label>Prénom</label>
        <input v-model="prenom" placeholder="votre prénom ici" :class='{ko: prenomKo}' />
        <p v-show="prenomKo" class="ko">Votre prénom doit comporter au moins 2 caractères...</p>
      </div>
      <p>
        <label>Civilité</label>
        <select v-model="civilite">
          <option value='' selected disabled>Choisissez votre civilité</option>
          <option value="f">Madame</option>
          <option value="m">Monsieur</option>
        </select>
        <!-- appel de la fonction testCivilite directement dans le template -->
        <span> {{ testCivilite }} </span>
      </p>
      <p>
        <button type="submit">Go !</button>
      </p>
      <p>{{ message }}</p>
    </form>
    <!-- appel de la fonction maDate (mise en cache)-->
    <p>{{ maDate }}</p>
  </div>
</template>

<script>

  export default {
    name: 'FormComponent',
    data() {
      return {
        nom: 'Toto',
        prenom: '',
        civilite: '',
        message: '',
        nomKo: false,
        prenomKo: false,
      }
    },
    watch: {
      //fonction pour surveiller la variable nom
      //2 params: la nouvelle valeur et l'ancienne
      nom(newVal, oldVal) {
        console.log(oldVal, newVal);
        if(newVal.length < 2 ) this.nomKo = true;
        else this.nomKo = false;
      },
      prenom(nVal) {
        if(nVal.length < 2 ) this.prenomKo = true;
        else this.prenomKo = false;
      }
    },
    /* fonctions avec mise en cache, sans params et obligatoirement valeur de retour */
    computed: {
      testCivilite() {
        let retour;
        if(this.civilite == 'f') retour = 'Madame';
        else if(this.civilite == 'm') retour = 'Monsieur';
        else retour = '';
        return retour; 
      },
      maDate() {
        return new Date().getFullYear();
      }
    },
    methods: {
      traitement() {
        //test si 2 caractères mini pour nom et prenom
       /* if(this.nom.length >= 2) this.nomKo = false;
        else this.nomKo = true;
        if(this.prenom.length < 2 ) this.prenomKo = true;
        else this.prenomKo = false;*/
//        console.log(this.nom, this.civilite);
        if(this.nomKo === false && this.prenomKo === false) 
          this.message = 'Bonjour ' 
                          + this.prenom 
                          + ' ' 
                          + this.nom;
      }
    },
    
  }
</script>

<style scoped>
.ko {
  border-color: #FF5555;
}
p.ko {
  background-color: #FF5555;
  color: white;
  padding: 2px;
}
</style>