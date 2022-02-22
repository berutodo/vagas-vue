<template>
  <div class="card">
                <div class="card-header bg-dark text-white ">
                    <div class="row">
                        <div class="col d-flex justify-content-between">
                            <div>{{titulo}}</div>
                            <div>
                                <div class="form-check form-switch">
                                    <input class='form-check-input' type="checkbox" v-model="favoritada">
                                    <label class='form-check-label'>Favoritar</label>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    </div>
                <div class="card-body">
                    <p>{{descricao}}</p>
                </div>
                <div class="card-footer">
                    <small class='text-muted'>Salário R$ {{salario}} | Modalidade : {{getModalidade}} | Tipo : {{getTipo}}  | Publicação : {{publicacao}}</small>
                </div>
            </div>
</template>

<script>
export default {
    name: 'Vaga',
    data: () => ({
        favoritada : false
    }),
    watch:{
        favoritada(valorNovo){
            if(valorNovo){
                return this.emitter.emit('favoritarVaga', this.titulo)
            }else{
                return this.emitter.emit('desfavoritarVaga', this.titulo)
            }
        }
    },
    props: ['titulo','descricao','salario','modalidade','tipo','publicacao'],
    computed: {
        getModalidade(){
            switch(this.modalidade){
                case '1' : return 'Home Office'
                case '2' : return 'Presencial'
            }
            return ''
        },
        getTipo(){
            switch(this.tipo){
                case '1' : return 'CLT'
                case '2' : return 'PJ'
            }
            return ''
        }
    },
    methods: {
    }
}
</script>

<style>

</style>