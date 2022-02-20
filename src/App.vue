<template>
  <TopoPadrao @navegar="componente = $event"/>
  <Conteudo :conteudo="componente"/>
</template>

<script>
import TopoPadrao from './components/layouts/TopoPadrao.vue'
import Conteudo from './components/layouts/Conteudo.vue'

export default {
  name: 'App',
  data(){
    return{
      componente: 'Home'
    }
  },
  components: {
    TopoPadrao,
    Conteudo
  },
  methods:{
  }
}
</script>

<style scoped>

</style>
