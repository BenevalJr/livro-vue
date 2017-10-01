<template>
  <div id="app">
    <!-- Exibindo tito com v-text e uma vez com v-once -->
    <h1 v-text="titulo"></h1>
    <h1 v-once v-text="titulo"></h1>

    <!-- Exibindo com mustache -->
    <h2>{{ subtitulo }}</h2>

    <!-- Input só aparece se não tiver nenhuma tarefa, e representa a variavel subtitulo -->
    <input :disabled="tarefas.length == 0" v-model="subtitulo" type="text">

    <!-- Caso não tenha tarefas -->
    <div v-if="tarefas.length  <=  0">
      Não há tarefas
    </div>

    <!-- Caso exista tarefas -->
    <div v-if="tarefas.length  > 0">
      Existem {{tarefas.length}} tarefas

      <!-- Percorre a lista de tarefas exibindo cada uma -->
      <ul>
        <li v-for="tarefa in tarefas">{{ tarefa }}</li>
      </ul>

      <!-- Executa a ação para redefinir lista de tarefas -->
      <button @click="tarefas = []">Limpar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      titulo: 'Listagem de tarefas',
      subtitulo: 'Defina uma descrição',
      tarefas: []
    }
  },
  // Executado quando o componente é montado, seta um titulo e algumas tarefas depois de 3 segundos
  mounted() {
    setTimeout(() => {
      this.titulo = "Novo título"
      this.tarefas = ['tarefa  1', 'tarefa 2', 'tarefa 3', 'tarefa 4' ]
    }, 3000 )
  }
}
</script>
