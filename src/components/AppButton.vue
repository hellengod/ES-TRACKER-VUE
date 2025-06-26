<template>
    <button class="button" @click="clicar" :disabled="habilitado">
        <span class="icon">
            <i :class="icon"></i>
        </span>
        <span>{{ funcao }}</span>
    </button>
</template>

<script lang="js">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'AppButton',
    props: {
        clicar: { type: Function, required: true },
        habilitado: { type: Boolean, required: true },
        icon: { type: String, required: true },
        funcao: { type: String, required: true },
    }

})
</script>