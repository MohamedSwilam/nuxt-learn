<template>
  <div>
    <div>
        <h2>Making API request - the nuxt way (SSR)</h2>
      <hr>
    </div>
    <div class="container row">
      <card v-for="post in posts" :key="post.id" :post="post" class="ml-auto mr-auto"></card>
      <button class="btn btn-danger" v-scroll-to="'body'">Back To Top</button>
    </div>
  </div>

</template>
<script>
    import axios from 'axios';
    import Card from "../../components/card";
    import {mapGetters} from 'vuex';

    export default {
        name: "index",
        components: {Card},
        head: {
            title: 'List Of Posts'
        },
        async fetch({store}) {
            let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');

            // use fetch
            store.dispatch('setPosts', data);

            // use async asyncData
            // return {posts: data};
        },
        data: () => {
            return {
                allPosts: [],
            }
        },
        computed: {
            ...mapGetters(['posts'])
            // posts() {
            //     console.log('ababa');
            //     console.log('here... ',this.$store.getters)
            //     return this.$store.getters['posts/posts'];
            // }
        },
        mounted() {

        }
    }
</script>

<style scoped>

</style>
