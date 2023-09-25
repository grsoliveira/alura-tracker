<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para Criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="descricao">
      </div>
      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";

export default defineComponent({
  name: 'FormularioTarefa',
  data() {
    return {
      descricao: ''
    }
  },
  components: {
    Temporizador
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      console.log('Tempo da tarefa ' + tempoDecorrido);
      console.log('Descricao da tarefa ' + this.descricao);

      this.descricao = '';
    }
  }
});
</script>
