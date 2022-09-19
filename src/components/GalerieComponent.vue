<template>
  <div class="galerie">
    <figure>
      <img src="../assets/img1.jpg" alt="img 1" />
      <figCaption>Image 1</figCaption>
    </figure>
    <figure>
      <img src="../assets/img2.jpg" alt="img 2" />
      <figCaption>Image 2</figCaption>
    </figure>
    <figure>
      <img src="../assets/img3.jpg" alt="img 3" />
      <figCaption>Image 3</figCaption>
    </figure>
    <figure>
      <img src="../assets/img4.jpg" alt="img 4" />
      <figCaption>Image 4</figCaption>
    </figure>
    <figure>
      <img src="../assets/img5.jpg" alt="img 5" />
      <figCaption>Image 5</figCaption>
    </figure>
    <figure>
      <img src="../assets/img6.jpg" alt="img 6" />
      <figCaption>Image 6</figCaption>
    </figure>
    <figure>
      <img src="../assets/img7.jpg" alt="img 7" />
      <figCaption>Image 7</figCaption>
    </figure>
    <figure>
      <img src="../assets/img8.jpg" alt="img 8" />
      <figCaption>Image 8</figCaption>
    </figure>
  </div>
</template>

<script>
  export default {
    name: 'GalerieComponent',

  }
</script>

<style scoped>
* {
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
}
.galerie figure img {
  max-width: 100%;
}
</style>