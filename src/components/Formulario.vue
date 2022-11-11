<template>
  <div class="box">
    <div class="columns">
      <div class="column is-9" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="descricao"/>
      </div>
      <div class="column">
        <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";

export default defineComponent({
  name: 'FormularioHome',
  components: {
    Temporizador,
  },
  data() {
    return {
      descricao: '',
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      console.log('Tempo decorrido: ', tempoDecorrido);
      console.log('Descrição: ', this.descricao);
      this.descricao = '';
    }
  }
})
</script>

