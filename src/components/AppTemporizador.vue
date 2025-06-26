<template>
    <div class="is-flex is-align-items-center is-justufy-content-space-between">
        <AppCronometro :tempoEmSegundos="tempoEmSegundos" />
        <AppButton :clicar="iniciar" :habilitado="cronometroRodando" icon="fas fa-play" funcao="play" />
        <AppButton :clicar="finalizar" :habilitado="!cronometroRodando" icon="fas fa-stop" funcao="stop" />

    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppCronometro from './AppCronometro.vue';
import AppButton from './AppButton.vue';
export default defineComponent({
    name: 'AppTemporizador',
    emtis: ['aoTemporizadorFinalizado'],
    components: {
        AppCronometro, AppButton
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
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos);
            this.tempoEmSegundos = 0;
        }
    }
})
</script>