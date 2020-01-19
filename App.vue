<template>
    <div class="container">
        <h1>Blog Posts</h1>
        <ul>
            <li v-for="post in posts" v-bind:key="post.title">
                <h2>{{ post.title }}</h2>
                <p>{{ post.author }}</p>
            </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios';

export default {

    data () {
        return {
            posts: []
        }
    },

    async mounted () {

        const url = 'http://167.172.117.35:8000/api/v1/'

        const response = await axios.get(url)

        this.posts = response.data
    }
}
</script>
<style>
    .container {
        background-color: aliceblue;
    }
    h1 {
        color: firebrick;
    }
</style>
