<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h4>Aprensente vagas para milhares de profissionais de graça</h4>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <label class="form-label">Titulo da Vaga</label>
        <input type="text" class="form-control" v-model='titulo'>
        <div class="form-text">Por Exemplo: Programador Javascript e Vuejs</div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <label class="form-label">Descrição</label>
        <textarea type="text" class="form-control" v-model="descricao"> </textarea>
        <div class="form-text">Informe os detalhes da vaga.</div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <label class="form-label">Salário</label>
        <input type="number" class="form-control" v-model='salario'>
        <div class="form-text">Informe o salário.</div>
      </div>
      <div class="col">
        <label class="form-label">Modalidade</label>
        <select class='form-select' v-model='modalidade'>
          <option value="" disabled>Selecione</option>
          <option value="1">Home Office</option>
          <option value="2">Presencial</option>
        </select>
        <div class="form-text">Informe a modalidade da vaga.</div>
      </div>
      <div class="col">
        <label class="form-label">Tipo</label>
        <select class='form-select' v-model="tipo">
          <option value="" disabled>Selecione</option>
          <option value="1">CLT</option>
          <option value="2">PJ</option>
        </select>
        <div class="form-text">Informe o tipo de vaga.</div>
      </div>
    </div>
    <div class="row">
      {{titulo}} | {{descricao}} | {{salario}} | {{modalidade}} | {{tipo}}  
      <div class="col">
        <button type="submit" class="btn btn-primary" @click="salvarVaga()">Cadastrar</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'PublicarVaga',
    data: () =>({
      titulo: '',
      descricao: '',
      salario: '',
      modalidade:'',
      tipo:'',
      data: new Date().getDate() + '/' + parseInt(new Date().getMonth() + 1) + '/' + new Date().getFullYear()
      }),
    components: {
    },
    methods: {
      salvarVaga(){

        let vagas = JSON.parse(localStorage.getItem('vagas'))
        console.log(vagas)
        if(!vagas) vagas = []
        let vaga = {
          titulo : this.titulo,
          descricao : this.descricao,
          salario : this.salario,
          modalidade : this.modalidade,
          tipo : this.tipo,
          publicacao : this.data
        }
        vagas.push(vaga)
        if(this.validacaoFormulario()){
        localStorage.setItem('vagas', JSON.stringify(vagas))
          this.emitter.emit('alerta', {
            tipo: 'sucesso',
            titulo: `A vaga ${this.titulo} foi cadastrada com sucesso`,
            subtitulo: 'Parabens sua vaga foi cadastrada e pode ser acessada por milhares de pessoas em todo o globo terrestre'
          })
        this.resetarFormulario()

        }else{
          this.emitter.emit('alerta', {
            tipo: 'erro',
            titulo: `Preenche essa merda direita seu corno 🐂`,
            subtitulo: 'Reveja seus dados e tente novamente :)'
          })
        }
        
      },
      resetarFormulario(){
        this.titulo = '',
        this.descricao = '',
        this.salario = '',
        this.modalidade = '',
        this.tipo = ''
      },
      validacaoFormulario(){
        let validator = true
        if(this.titulo === '') validator = false
        if(this.descricao === '') validator = false
        if( this.salario === '') validator = false
        if(this.modalidade === '') validator = false
        if(this.tipo === '') validator = false
        return validator
      }
    }
}
</script>

<style>

</style>