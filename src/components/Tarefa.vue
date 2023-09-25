<template>
  <div class="box has-text-wight-bold">
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao }}
      </div>
      <div class="column">
        <CronometroComp :tempoEmSegundos="tarefa.duracaoEmSegundos" />
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import {defineComponent, PropType} from "vue";
import CronometroComp from "@/components/Cronometro.vue";
import ITarefa from "@/interfaces/ITarefa";

export default defineComponent({
  name: 'TarefaComp',
  components: {
    CronometroComp
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  }
})
</script>


<style scoped>
.box {
  background: #FAF0CA;
}
</style>
