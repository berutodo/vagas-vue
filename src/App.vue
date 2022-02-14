<template>
  <h1>Teste</h1>
  <TopoPadrao/>
  <Conteudo />
</template>

<script>
import TopoPadrao from './components/layouts/TopoPadrao.vue'
import Conteudo from './components/layouts/Conteudo.vue'

export default {
  name: 'App',
  components: {
    TopoPadrao,
    Conteudo
  }
}
</script>

<style scoped>

</style>
