<template>
    <div class="alert alert-success" role="alert">
        <slot name="titulo"><h1>Alerta</h1></slot>
        <hr>
        <slot name="subtitulo"><h2>Subtitulo</h2></slot>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name : 'Alerta'
}
</script>

<style scoped>
</style>