<template>

    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criacao de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa voce deseja inciar?" v-model="descricao">
            </div>
            <div class="column">
                <AppTemporizador @aoTemporizadorFinalizado="finalizarTarefa" />
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
    data() {
        return {
            descricao: ''
        }
    },
    methods: {
        finalizarTarefa(tempoDecorrido: number): void {
            console.log(tempoDecorrido)
            console.log(this.descricao)
            this.descricao=''
        }
    }
})
</script>

<style scoped></style>