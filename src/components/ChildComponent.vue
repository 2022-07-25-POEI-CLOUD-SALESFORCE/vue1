<template>
  <div class="child">
    <h1>Composant Enfant</h1>
    <!-- local est une variable du composant définie dans data-->
    <p>{{ local }}</p>
    <!-- message est une variable "vide" dont le contenu est transmis par le parent -->
    <p>{{ message }}</p>
    <p>{{ message2.id }} {{ message2.nom }} {{ message2.prenom }}</p>
    <button @click="actionLocale">Local</button>
    <button @click="actionParent">Parent</button>
  </div>
</template>

<script>
  export default {
    name: 'ChildComponent',
    /* on définit les propriétés (avec leur style) envoyées par le composant parent */
    props: {
      message: String,
      message2: Object
    },
    // props: [message, message2],
    data() {
      return {
        local: 'message reçu'
      }
    }, 
    methods: {
      actionLocale() {
        alert('Action Locale');
      },
      actionParent() {
        //emission d'un évènement vers le parent
        //this.$emit(nom de l'évènement, paramètre d'envoi)
        this.$emit('mareponse', this.local);

      }
    }
  }
</script>

<style scoped>
  .child {
    background: white;
    width: 60%;
    margin: 0 auto;
  }
</style>