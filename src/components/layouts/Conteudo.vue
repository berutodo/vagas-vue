<template>
    <component :is="conteudo"></component>
    
</template>

<script>
import Home from '../views/Home.vue'
import PublicarVaga from '../views/PublicarVaga.vue'
export default {
    

    name: 'Conteudo',
    props:{
        conteudo:{
            type: String,
            required: true
        }
    },
    components: {
        Home,
        PublicarVaga
    },

}
</script>

<style scoped>
    
</style>