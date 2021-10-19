<template>
  <div class="container">
    <h2>{{ titulo }}</h2>
  <div class="container">
    <div class="input-group">
      <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text" />
      <span>
        <button @click="adicionarTarefa">
          Adicionar tarefa
        </button>
      </span>
    </div>
    <ul>
      <li
        v-for="(tarefa, index) in tarefas"
        :key="index"
        :class="{ removed: tarefa.checked }"
      >
        <input type="checkbox" class="removed-li" v-model="tarefa.checked"  />
        <label>{{ tarefa.titulo }}</label>
      </li>
    </ul>
    <footer>
      <em></em>
      <input v-model="titulo" type="text" value="a" />
    </footer>
  </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      titulo: "Escolha o titulo:",
      novaTarefa: "",
      tarefas: [
        
      ],
    };
  },
  methods: {
    adicionarTarefa() {
      this.tarefas.push({
        titulo: this.novaTarefa,
        checked: false,
      });
      this.novaTarefa = "";
    },
  },
};
</script>

<style>
body{
  margin:0px;
  padding:0px;
  background-color:#B0E0E6;
}
input{
  background-color:#d5e6e9;
  border:#B0E0E6;
}
button{
  background-color:#B0E0E6;
  border: #B0E0E6 solid 10px;
  border-bottom-color:rgba(51, 51, 105, 0.212) ;
}
.container {
  width: 90%;
  height:50% ;
  justify-content:space-between;
  text-align: justify;
  margin: 50px auto 50px auto;
  padding:10px 10px 10px 10px;
  border:10px double #B0E0E6;
  border-left-color: slateblue;
  border-right-color:slateblue;
  display:flex;
  flex-wrap: wrap;
}
ul li {
  border:1px #B0E0E6 solid  ;
  border-left-color: slateblue;
  list-style:none;
  border-radius:20%;
}
.removed {
}
.removed label {
  background-color:snow;
  text-decoration: line-through;
}
</style>
