<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        Descrição da tarefa
      </div>
      <div class="column">
        <Cronometro tempo-em-segundos="15"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import Cronometro from "@/components/Cronometro.vue";

export default defineComponent({
  name: 'Tarefa',
  components: {
    Cronometro,
  },
})
</script>

<style scoped>
.box {
  background: #FAF0CA;
}
</style>