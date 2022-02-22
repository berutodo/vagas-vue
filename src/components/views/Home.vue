<template>
    <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga :vagas="vagas"/>
      </div>
    </div>
    <div class="row mt-5" v-for="(vaga ,index) in vagas" :key='index'>
        <div class="col">
            <vaga 
                v-bind="vaga"
            />
        </div>
    </div>
    
    <div class="row mt-5">
      <div class="col-4">
        <indicador titulo="Vagas de Dev " :numeroVagas="67" bg="bg-dark" color="text-white"/>
      </div>

      <div class="col-4">
        <indicador titulo="Profissão Reporter" :numeroVagas="29" bg="bg-dark" color="text-white" />
      </div>
    
      <div class="col-4">
        <indicador titulo="Quantidade de acessos" :numeroVagas="usuariosOnline" bg="bg-light" color="text-dark"/>
      </div>
    </div>
  </div>
</template>

<script>
import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue'
import Indicador from '../comuns/Indicador.vue'
import Vaga from '../comuns/Vaga.vue'
export default {
    name: "Home",
    components: {
        PesquisarVaga,
        Indicador,
        Vaga
    },
    data: () => ({
        usuariosOnline : 0,
        vagas: [],
    }),
    methods: {
        getUsuarioOnline() {
            this.usuariosOnline = Math.floor(Math.random() * 101 )
        },
    },
    created(){
        setInterval(this.getUsuarioOnline, 2000)
    },
    mounted(){
      this.vagas = JSON.parse(localStorage.getItem('vagas'))
    }
    
}

</script>

<style module>
.TituloPagina {
    color: red;
    background-color: green;
}

</style>