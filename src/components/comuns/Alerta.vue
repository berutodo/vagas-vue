<template>
    <div :class="definirAlerta" role="alert">
        <slot name="titulo"><h1>Alerta</h1></slot>
        <hr>
        <slot name="subtitulo"><h2>Subtitulo</h2></slot>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name : 'Alerta',
    props: {tipo : String},
    computed: {
        definirAlerta(){
            switch(this.tipo){
                case 'erro': return 'alert alert-danger'
                case 'sucess': return 'alert alert-sucess'
                default: return 'alert alert-sucess'
            }
        }
    }
}
</script>

<style scoped>
</style>