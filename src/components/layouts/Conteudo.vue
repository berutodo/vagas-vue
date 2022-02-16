<template>
    <h1>Conteudo</h1>
    <button @click="conteudo = 'home'">Home</button>
    <button @click="conteudo = 'publicar-vaga'">Publicar Vaga</button>
   <!-- <home />
    <publicar-vaga /> -->
    <component :is="conteudo"></component>

    
</template>

<script>
import Home from '../views/Home.vue'
import PublicarVaga from '../views/PublicarVaga.vue'
export default {
    

    name: 'Conteudo',
    components: {
        Home,
        PublicarVaga
    },
    data: () => ({
        conteudo: 'home'
    })

}
</script>

<style scoped>
    
</style>