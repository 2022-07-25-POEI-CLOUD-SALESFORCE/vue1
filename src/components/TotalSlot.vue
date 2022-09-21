<template>
  <div class="total">
    <!-- un slot sert uniquement à faire de l'affichage -->
    <slot></slot> Projets
  </div>
</template>

<script>
  export default {
    name: 'TotalSlot'
  }
</script>

<style scoped>
  .total {
    font-size: 2em;
    font-family: Verdana;
    color: red;
    text-shadow: 2px 2px 2px orange;
  }
</style>