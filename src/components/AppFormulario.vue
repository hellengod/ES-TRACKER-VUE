<template>

    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criacao de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa voce deseja inciar?">
            </div>
            <div class="column">
                <AppTemporizador />
            </div>
        </div>
    </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppTemporizador from './AppTemporizador.vue';
export default defineComponent({
    name: 'AppFormulario',
    components: {
        AppTemporizador
    },
})
</script>

<style scoped></style>