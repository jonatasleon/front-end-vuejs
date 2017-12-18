<template>
<div id="app">
  <!-- <h1 v-once>{{ titulo }}</h1>
  <h2>{{ subtitulo }}</h2>
  <div>
    <input :disabled="tarefas.length == 0" v-model="subtitulo" type="text" placeholder="Descrição">
  </div>
  <div v-if="tarefas.length <= 0">
    Não há tarefas
  </div>
  <div v-if="tarefas.length > 0">
    Existem {{ tarefas.length }} tarefas
    <ul>
      <li v-for="tarefa in tarefas">{{ tarefa }}</li>
    </ul>
  </div>
  <button @click="tarefas = []">Limpar</button>
  <hr> -->
  <h1 v-text="nome"></h1>
  <small v-if="verSmall" v-once v-text="nome"></small>
  <div>
    <input type="text" v-model="nome" placeholder="Nome">
  </div>
  <button :disabled="disableButton" type="button" @click="verSmall = !verSmall">Toggle small</button>
  <ul>
    <li v-for="cadeira in cadeiras">{{ cadeira }}</li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'lv-tarefas',
  data() {
    return {
      titulo: 'Listagem de tarefas',
      subtitulo: 'Defina uma descrição',
      tarefas: [],
      nome: "Mané Garrincha",
      verSmall: true,
      disableButton: true,
      cadeiras: ['30.000 brancas', '30.000 cinzas', '10.000 vips']
    }
  },
  mounted() {
    setTimeout(() => {
      this.titulo = 'Novo título zica'
      this.tarefas = ['Tarefa 1', 'Tarefa 2', 'Tarefa 3', 'Tarefa 4']
    }, 2000)
    setTimeout(() => {
      this.nome = 'Mineirão'
      this.disableButton = false
    }, 4000);
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
