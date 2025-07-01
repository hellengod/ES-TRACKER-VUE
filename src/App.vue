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
export default defineComponent({
  name: 'App',
  components: { BarraLateral, AppFormulario }
});
</script>

<style></style>
