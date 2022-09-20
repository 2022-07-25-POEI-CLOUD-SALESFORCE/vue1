<template>
  <div class="tabs">
    <ul>
      <!-- une fonction liée au clic à laquelle on passe l'onglet à afficher -->
      <li @click="show(1)" :class="{active: t1}">Tab 1</li>
      <li @click="show(2)" :class="{active: t2}">Tab 2</li>
      <li @click="show(3)" :class="{active: t3}">Tab 3</li>
      <li @click="show(4)" :class="{active: t4}">Tab 4</li>
    </ul>
    <!-- le premier onglet sera affiché si t1 vaut true -->
    <div v-show="t1" :class="{active: t1}">
      <h1>Premier onglet</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore at doloribus cumque explicabo nisi consectetur id nesciunt eligendi possimus vero laborum perferendis, veritatis quae est placeat? Inventore officiis minima porro!</p>
    </div>
    <div v-show="t2" class="active">
      <h1>Deuxième onglet</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore at doloribus cumque explicabo nisi consectetur id nesciunt eligendi possimus vero laborum perferendis, veritatis quae est placeat? Inventore officiis minima porro!</p>
    </div>
    <div v-show="t3" class="active">
      <h1>Troisième onglet</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore at doloribus cumque explicabo nisi consectetur id nesciunt eligendi possimus vero laborum perferendis, veritatis quae est placeat? Inventore officiis minima porro!</p>
    </div>
    <div v-show="t4" class="active">
      <h1>Quatrième onglet</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore at doloribus cumque explicabo nisi consectetur id nesciunt eligendi possimus vero laborum perferendis, veritatis quae est placeat? Inventore officiis minima porro!</p>
    </div>
    </div>
</template>

<script>
  export default {
    name: 'TabsComponent',
    data() {
      return {
        t1: true,
        t2: false,
        t3: false,
        t4: false
      }
    },
    methods: {
      //la fonction liée au clic sur un onglet. On lui passe 1,2,3 ou 4
      // pour savoir quel onglet afficher 
      show(id) {
        //on cache tous les onglets
        //this.t1 = this.t2 = this.t3 = this.t4 = false;
        this.t1 = false;
        this.t2 = false;
        this.t3 = false;
        this.t4 = false;
        //on active l'onglet demandé 
        if(id === 1) this.t1 = true;
        else if(id === 2) this.t2 = true;
        else if(id === 3) this.t3 = true;
        else this.t4 = true;
      }
    }
  }
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  text-align: left;
}
li {
  display: inline-block;
  border: 1px solid red;
  padding: 10px;
  margin: 0;
  border-radius: 10px 10px 0px 0px;
}
div {
  text-align: left;
  margin: 0;
  padding: 10px;
  font-size: 1.2em;
}
.active {
  background-color: red;
}
.inactive {
  color: red;
}
li.active {
  border-bottom: 1px solid red;
  color: white;
}

</style>