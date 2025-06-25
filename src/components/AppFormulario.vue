<template>

    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criacao de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa voce deseja inciar?">
            </div>
            <div class="column">
                <div class="is-flex is-align-items-center is-justufy-content-space-between">
                    <AppCronometro :tempoEmSegundos="tempoEmSegundos" />
                    <button class="button">
                        <span class="icon">
                            <i class="fas fa-play"></i>
                        </span>
                        <span @click="iniciar()">play</span>
                    </button>
                    <button class="button">
                        <span class="icon">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span @click="finalizar()">stop</span>
                    </button>
                </div>
            </div>
        </div>
    </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppCronometro from './AppCronometro.vue';
export default defineComponent({
    name: 'AppFormulario',
    components: {
        AppCronometro
    },
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
        }
    },

    methods: {
        iniciar() {
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        finalizar() {
            clearInterval(this.cronometro);
            // this.tempoEmSegundos = 0;
        }
    }
})
</script>

<style scoped></style>