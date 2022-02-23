<template>
    <div class="row mt-5" v-for="(vaga ,index) in vagas" :key='index'>
        <div class="col">
            <vaga 
                v-bind="vaga"
            />
        </div>
    </div>
</template>

<script>
import Vaga from '../comuns/Vaga.vue'

export default {
    name: 'ListaVagas',
    data: () => ({
        vagas: []
    }),
    components: {
        Vaga,
    },
    mounted(){
      this.vagas = JSON.parse(localStorage.getItem('vagas'))
      this.emitter.on('filtrarVaga', vaga => {
        const vagas = JSON.parse(localStorage.getItem('vagas'))
         this.vagas = vagas.filter(el => el.titulo.toLowerCase().includes(vaga.toLowerCase()))
      })
    }
}
</script>

<style>

</style>