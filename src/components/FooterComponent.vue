<template>
  <footer>
    Copyright &copy; {{ new Date().getFullYear() }} - Moi <a href="mentions.html">Mentions légales</a>
  </footer>
</template>

<script>
  export default {
    name: 'FooterComponent',
    data() {
      return {

      }
    }
  }

</script>

<style scoped>
footer {
  background: black;
  color: white; 
  padding: 20px;
  margin-top: 10px; 
}
footer a {
  color: white;
}
</style>