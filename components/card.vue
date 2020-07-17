<template>
    <div>
      <div class="card bg-light mb-3" style="max-width: 18rem;">
        <div class="card-header"><nuxt-link :to="{name: 'posts-id', params:{id: post.id}}">Post: {{post.id}}</nuxt-link></div>
        <div class="card-body">
          <h5 class="card-title">{{post.title}}</h5>
        </div>
      </div>
    </div>
</template>

<script>

    export default {
        name: "card",
        props: {
            post: Object
        }
    }
</script>

<style scoped>

</style>
