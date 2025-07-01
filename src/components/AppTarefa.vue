

<template>
    <div class="box has-text-wight-bold">
        <div class="columns">
            <div class="column is-7">
                Descricao da tarefa
            </div>
            <div class="column">
                <AppCronometro/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppCronometro from './AppCronometro.vue';
export default defineComponent({
    name: 'AppTarefa', 
    components: {AppCronometro},
})
</script>