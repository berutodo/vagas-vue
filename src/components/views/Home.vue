<template>
    <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga :vagas="vagas"/>
      </div>
    </div>
    <lista-vagas/>
    <!--
    
    -->
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
import ListaVagas from '../comuns/ListaVagas.vue'
export default {
    name: "Home",
    components: {
        PesquisarVaga,
        Indicador,
        ListaVagas,
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
    activated(){
    },
    
    
}

</script>

<style module>
.TituloPagina {
    color: red;
    background-color: green;
}

</style>