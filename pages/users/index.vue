<template>
  <div>
      <h1>Hello Users</h1>
      <input type="text" v-model="id">
      <button @click="loadUser">Load User</button>
  </div>
</template>

<script>
    export default {
        name: "index",
        data: () => {
            return {
                id: ''
            }
        },
        methods: {
            loadUser()
            {
                this.$router.push(`/users/${this.id}`);
            }
        }
    }
</script>

<style scoped>

</style>
