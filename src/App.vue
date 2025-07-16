<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <AppFormulario />
      <div class="lista">
        <AppTarefa/>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import AppFormulario from './components/AppFormulario.vue';
import AppTarefa from './components/AppTarefa.vue';
export default defineComponent({
  name: 'App',
  components: { BarraLateral, AppFormulario, AppTarefa },
});
</script>

<style>
.lista {
    padding: 1.25rem;
}
</style>
