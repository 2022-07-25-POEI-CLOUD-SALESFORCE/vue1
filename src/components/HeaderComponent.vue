<template>
  <header>
    <img src="../assets/logo.png" alt="mon super logo" />
    <div>
      <h1>{{ nom }} {{ prenom }}</h1>
      <h2>{{ ville }}</h2>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'HeaderComponent',
    data() {
      return {
        nom: 'TAVERNIER',
        prenom: 'Bruno',
        ville: 'Montpellier'
      }
    }
  }

</script>

<style scoped>
header {
  display: flex;
}
header img {
  width: 200px;
}
header div {
  margin-left: 30px;
  text-align: left;
}
</style>