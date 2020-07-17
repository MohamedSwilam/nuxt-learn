<template>
  <h1>Hello User id {{$route.params.id}}</h1>
</template>

<script>
    export default {
        name: "index",
        validate({params}) {
            return /^\d+$/.test(params.id)
        }
    }
</script>

<style scoped>

</style>
