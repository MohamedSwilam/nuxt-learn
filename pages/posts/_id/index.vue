<template>
    <div class="container">
      <h1>{{post.title}}</h1>
      <pre>{{post.body}}</pre>
      <nuxt-link to="/posts">Back</nuxt-link>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: "index",
        head() {
            return {
                title: this.post.title
            }
        },
        data: () => {
            return {
                post: null
            }
        },
        async asyncData({params}) {
            let {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
            return {post: data}
        }
    }
</script>

<style scoped>

</style>
