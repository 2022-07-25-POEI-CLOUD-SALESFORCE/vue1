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
        <input v-model.lazy="nom" placeholder="votre nom ici" />
        <span> {{ nom }} </span>
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
    </form>
  </div>
</template>

<script>
  export default {
    name: 'FormComponent',
    data() {
      return {
        nom: 'Toto',
        civilite: ''
      }
    },
    methods: {
      traitement() {
        console.log(this.nom, this.civilite);
      }
    }
  }
</script>

<style scoped>

</style>