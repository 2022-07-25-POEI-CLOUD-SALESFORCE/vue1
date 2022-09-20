<template>
  <div class="parent">
    <h1>Composant Parent</h1>
    <!-- on envoie des paramètres au composant enfant via des propriétés 
        ces paramètres peuvent être des chaines, des nombres ou carrément des objets 
        l'enfant peut répondre au parent par un évènement qu'il faudra écouter et traiter -->
    <ChildComponent :message="msg" :message2="msg2" @mareponse="reponseChild" />
    <p v-show="reponse"> {{ reponse }}</p>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';
  export default {
    name: "ParentComponent",
    data() {
        return {
            msg: "Hello World !",
            msg2: { id: 1, nom: "MARCEL", prenom: "Benhur" },
            reponse: false
        };
    },
    methods: {
      //traitement de la réponse à l'évènement déclenché par le composant enfant
      reponseChild(e) {
        console.log(e);
        this.reponse = e;
      }
    },
    components: { ChildComponent }
}
</script>

<style scoped>
  .parent {
    background: silver;
  }
</style>