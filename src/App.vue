<template>
  <main class="columns is-gapless is-multiline">
    <div class="columm is-one-quarter">
      <BarraLateral />
    </div>
    <div class="columm is-three-quarter">
      <FormularioHome />
      <div class="lista">
        <Tarefa />
        <Tarefa />
        <Tarefa />
        <Tarefa />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from "@/components/BarraLateral.vue";
import FormularioHome from "@/components/Formulario.vue";
import Tarefa from "@/components/Tarefa.vue";

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioHome,
    Tarefa,
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
