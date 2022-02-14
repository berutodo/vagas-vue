<template>
    <h1>Conteudo</h1>
    <home />
    <publicar-vaga />
    
</template>

<script>
import Home from '../views/Home.vue'
import PublicarVaga from '../views/PublicarVaga.vue'

export default {
    name: 'Conteudo',
    components: {
        Home,
        PublicarVaga
    }

}
</script>

<style scoped>
    
</style>