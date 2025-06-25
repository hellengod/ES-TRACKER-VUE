<template>
    <div class="is-flex is-align-items-center is-justufy-content-space-between">
        <AppCronometro :tempoEmSegundos="tempoEmSegundos" />
        <button class="button" :disabled="cronometroRodando">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span @click="iniciar()">play</span>
        </button>
        <button class="button" :disabled="!cronometroRodando">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span @click="finalizar()">stop</span>
        </button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppCronometro from './AppCronometro.vue';
export default defineComponent({
    name: 'AppTemporizador',
    components: {
        AppCronometro
    },
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false,
        }
    },

    methods: {
        iniciar() {
            this.cronometroRodando = true
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000);
        },
        finalizar() {
            this.cronometroRodando = false

            clearInterval(this.cronometro);
            // this.tempoEmSegundos = 0;
        }
    }
})
</script>