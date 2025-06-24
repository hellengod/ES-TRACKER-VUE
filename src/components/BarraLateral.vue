<template>
    <header>
        <h1>

            <img src="../assets/logo.png" alt="logo tracker">

        </h1>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    name: 'BarraLateral'
})
</script>

<style scoped>
header {
    padding: 1rem;
    background: #e9e3d2;
    width: 100%;
    height: 100vh;
}

img {
    border-radius: 20px;
}

@media only screen and (max-width: 768px) {
    header {
        padding: 2.5rem;
        height: auto;
    }
}
</style>