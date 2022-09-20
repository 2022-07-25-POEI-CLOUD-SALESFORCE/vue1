<template>
  <div class="form">
    <form @submit.prevent="traitement"> 
      <p>
        <label>Nom</label>
        <!-- v-model : liaison bi-directionnelle html<->JS 
             v-model.lazy : mise à jour sur le blur plutot que sur le change 
             v-model.trim : suppression des espaces avant et après le texte
             v-model.number : nombre uniquement
        -->
        <input v-model.lazy="nom" placeholder="votre nom ici" :class='{ko: nomKo}' />
        <span v-show="nomKo" class="ko">Votre nom doit comporter au moins 2 caractères...</span>
      </p>
      <p>
        <label>Prénom</label>
        <input v-model="prenom" placeholder="votre prénom ici" :class='{ko: prenomKo}' />
        <span v-show="prenomKo" class="ko">Votre prénom doit comporter au moins 2 caractères...</span>
      </p>
      <p>
        <label>Civilité</label>
        <select v-model="civilite">
          <option value='' selected disabled>Choisissez votre civilité</option>
          <option value="f">Madame</option>
          <option value="m">Monsieur</option>
        </select>
        <span> {{ civilite }} </span>
      </p>
      <p>
        <button type="submit">Go !</button>
      </p>
      <p>{{ message }}</p>
    </form>
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
    methods: {
      traitement() {
        //test si 2 caractères mini pour nom et prenom
        if(this.nom.length >= 2) this.nomKo = false;
        else this.nomKo = true;
        if(this.prenom.length < 2 ) this.prenomKo = true;
        else this.prenomKo = false;
//        console.log(this.nom, this.civilite);
        if(this.nomKo === false && this.prenomKo === false) this.message = 'Bonjour ' + this.prenom + ' ' + this.nom;
      }
    }
  }
</script>

<style scoped>
.ko {
  border-color: #FF5555;
}
span.ko {
  background-color: #FF5555;
  color: white;
  padding: 2px;
}
</style>