<template>
  <button class="button">{{content ? content : 'Digite algo'}} </button>
</template>

<script>
export default {
    name: 'Button',
    props:{
        content : String
    }
}
</script>

<style>

</style>