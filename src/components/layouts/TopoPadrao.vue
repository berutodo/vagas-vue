<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">Vagas</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
            <a class="nav-link" aria-current="page" href="#" @click="navegarPara('Home')">Home</a>
            <a class="nav-link" href="#" @click="navegarPara('PublicarVaga')">Publicar Vaga</a>
        </div>
        </div>
    </div>
    </nav>
</template>

<script>

export default {
    name: 'TopoPadrao',
    props:{
    },
    methods:{
        navegarPara(p){
            console.log(p)
            this.$emit('navegar',p)    
        }
    },
    components: {
    }
}
</script>

<style>
.button {
    margin-top: 10px;
}
.header {
    width : 100%;
    height: 200px;
    background-color : red;
}

</style>