<template>
  <div class="h-100 p-5 bg-light border rounded-3">

          <h2>Pesquisar Vagas</h2>
          <div class="row">
            <div class="col">
              <div class="form-group">
                <label>Título da vaga</label>
                <input type="text" v-model="pesquisa" @keyup="fazerPesquisa" class="form-control" placeholder="Pesquise por palavras chaves, por exemplo 'PHP', 'Pleno', 'Analista'">
                <small class="form-text text-muted">Informe palavras que estejam relacionadas com o título da vaga que você procura</small>
              </div>
              <p v-for="(v,index) in result" :key="index">
                  {{v.titulo}}{{v.tipo}}</p>
              <hr>
              {{vagas}}
            </div>
          </div>
          <div class="row">
            <div class="col">
              <button class="btn btn-outline-dark mt-2" type="button">Buscar</button>
            </div>
          </div>
          </div>
</template>

<script>

export default {
    name: 'PesquisaVaga',
    components: {
        
    },
    data: () => ({
        pesquisa: '',
        result: []
    }),
    props: ['vagas'],
    computed: {
        
    },
    methods: {
fazerPesquisa(){ //Pesquisa das vagas recebidas no props que vao ser enviadar para result e ser exibidas
        this.result = this.vagas.filter(vagas => vagas.tipo == this.pesquisa)
        return console.log(this.result)
        }
    }
}
</script>

<style>

</style>