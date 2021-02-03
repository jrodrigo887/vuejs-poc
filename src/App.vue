<template>
  <div id="app">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h1>Meu Jogo Favorito</h1>
    <ol class="list-games">
    <meuGameFavorito v-for="item in jogos" 
    :key="item.id" 
    :nome="item.nome"
    >
    </meuGameFavorito>
    </ol>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import MeuGameFavorito from './components/meuGameFavorito.vue'

export default {
  name: 'App',
  data() {
    return {
      jogos: []
    }
  },
  components: {
    // HelloWorld,
    MeuGameFavorito,
  },
  mounted() {
    this.fetchDatas();
  },
  methods: {
    async fetchDatas() {
      const result = await fetch("jogos.json")
      const jsonData = await result.json();
      this.jogos = jsonData;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #81b7ee;
  margin-top: 60px;
}
.list-games{
  border-radius: 2px;
  /* background-color: #99aab5; */
  background: linear-gradient(45deg, #99aab5, #5d6d81);
  padding: 10px;
}

body{
  padding: 0px;
  background-color: #23272a;
}
</style>
