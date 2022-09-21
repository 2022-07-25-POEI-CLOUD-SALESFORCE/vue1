<template>
  <div :class="projet.etat">
    <h1>{{ projet.nom }}</h1>
    <button v-show="projet.etat=='ouvert'" @click="fermer">Fermer</button>
  </div>
</template>

<script>
  export default {
    name: 'ProjetComponent',
    props: {
      projet: Object
    },
    methods: {
      fermer() {
        //on retourne l'ID du projet que le parent devra fermer
        this.$emit('fermer', this.projet.id);
      }
    }

  }
</script>

<style>
.ouvert {
  background: palegreen;
}
.ferme {
  background: lightcoral;
}
</style>