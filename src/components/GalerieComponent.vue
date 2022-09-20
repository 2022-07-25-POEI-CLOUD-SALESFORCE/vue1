<template>
  <div class="galerie">
    <!-- une figure permet de lier une image et une légende -->
    <figure @click="open" >
      <img src="../assets/img1.jpg" alt="img 1" ref="img1"/>
      <figcaption>Image 1</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img2.jpg" alt="img 2" />
      <figcaption>Image 2</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img3.jpg" alt="img 3" />
      <figcaption>Image 3</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img4.jpg" alt="img 4" />
      <figcaption>Image 4</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img5.jpg" alt="img 5" />
      <figcaption>Image 5</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img6.jpg" alt="img 6" />
      <figcaption>Image 6</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img7.jpg" alt="img 7" />
      <figcaption>Image 7</figcaption>
    </figure>
    <figure @click="open">
      <img src="../assets/img8.jpg" alt="img 8" />
      <figcaption>Image 8</figcaption>
    </figure>
    <div id="popup" v-show="show" @click="close">
      <img :src="active" />
    </div>
  </div>
</template>


<script>
  export default {
    name: 'GalerieComponent',
    data() {
      return {
        active: '',
        show: false
      }
    },
    // mounted (page chargée et ready)
    // utilisé pour des appels d'API, les corrections d'affichage ou masquage d'éléments, ...
    mounted() {
      this.show = false;
      this.disabled = true;
      //accès aux infos d'un élément par sa ref
      console.log(this.$refs.img1.src);
      console.log(this.$refs.img1.alt);
      //console.log(this.$el); //les éléments du DOM
    },
    /* hook de mise à jour terminée */
    updated() {
      console.log('updated');
    },
    methods: {
      open(event){
        //console.log(event.target.src);
        //on récupère le src de l'image dans l'évènement clic (target)
        // on le place dans le src de l'image de la popup
        this.active = event.target.src;
        //on affiche la popup (v-show)
        this.show = true;
      },
      //fermeture de la popup liée au clic sur cell ci
      close() {
        this.show = false;
      }
    }
  }
</script>

<style scoped>
* {
  /* la taille de l'élément est lié à sa bordure, padding exclu */
  box-sizing: border-box;
}
.galerie {
  display: flex;
  justify-content: space-around;
  row-gap: 2%;
  flex-wrap: wrap;
  width: 100%;
  padding: 15px;
  margin: 0;
  background-color: darkgray;
}
.galerie figure {
  width: 23%;
  margin: 10px 0 10px 0;
  background: white;
  font-size: 1.5em;
  padding: 5px;
}
.galerie figure img {
  /* pour éviter que l'image ne pousse son conteneur */
  max-width: 100%;
}
/* la popup d'affichage en grand */
#popup {
  position: absolute;
  left: 0;
  top: 0;
  /* centrage de l'image dans la popup */
  display: flex;
  align-items: center; /* centrage vertical */
  justify-content: center; /* centrage horizontal */
  width: 100vw;
  height: 100vh;
  z-index: 10;
  background-color: rgba(0, 0, 0, .9);
}

</style>