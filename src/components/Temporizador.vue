<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <Cronometro :tempoEmSegundos="tempoEmSegundos"/>
    <Botao @aoClicar="iniciar" :desabilitado="cronometroRodando" icone="fas fa-play" texto="play"/>
    <Botao @aoClicar="finalizar" :desabilitado="!cronometroRodando" icone="fas fa-stop" texto="stop"/>
  </div>
</template>

<script lang="ts">
import Cronometro from "@/components/Cronometro.vue"
import {defineComponent} from "vue";
import Botao from "@/components/Botao.vue";

export default defineComponent({
  name: 'Temporizador',
  emits: ['aoTemporizadorFinalizado'],
  components: {
    Botao,
    Cronometro
  },
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false,
    }
  },
  methods: {
    iniciar() {
      this.cronometroRodando = true;
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos+=1;
      }, 1000);
    },
    finalizar() {
      this.cronometroRodando = false;
      clearInterval(this.cronometro);
      this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos);
      this.tempoEmSegundos = 0;
    }
  }
})
</script>