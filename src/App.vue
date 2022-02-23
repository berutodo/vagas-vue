<template>
  <vagas-favoritas />
  <TopoPadrao @navegar="componente = $event"/>
  <alerta v-if="exibirAlerta" :tipo="this.alerta.tipo">
    <template v-slot:titulo>{{alerta.titulo}}</template>
    <template v-slot:subtitulo>{{alerta.subtitulo}}</template>
  </alerta>
  <keep-alive>
  <Conteudo :conteudo="componente"/>
  </keep-alive>
</template>

<script>
import TopoPadrao from './components/layouts/TopoPadrao.vue'
import Conteudo from './components/layouts/Conteudo.vue'
import VagasFavoritas from './components/comuns/VagasFavoritas.vue'
import Alerta from './components/comuns/Alerta.vue'

export default {
  name: 'App',
  data(){
    return{
      componente: 'Home',
      exibirAlerta: false,
      alerta: { titulo: '', subtitulo: '', tipo: ''}
    }
  },
  components: {
    TopoPadrao,
    Conteudo,
    VagasFavoritas,
    Alerta
  },
  mounted(){
    this.emitter.on('alerta', (a) => {
      this.alerta = a
      console.log(this.alerta)
      this.exibirAlerta = true
      setTimeout(() => this.exibirAlerta = false, 2000)
      console.log('Emitindo alerta')
    })
  }
}
</script>

<style scoped>

</style>
