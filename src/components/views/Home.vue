<template>
    <div>
      <h1 :class="$style['TituloPagina']">Home</h1>
    </div>
</template>

<script>
export default {
    name: "Home"
}
</script>

<style module>
.TituloPagina {
    color: red;
    background-color: green;
}

</style>