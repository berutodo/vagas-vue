<template>
  <div :class="`h-100 p-5 rounded-3 border ${bg} ${color}`">
          <p >{{titulo}}</p>
          <h2 >{{numeroVagas}}</h2>
        </div>
</template>

<script>
export default {
    name: 'Indicador',
    props: ['titulo','numeroVagas','bg','color']
}
</script>

<style>

</style>