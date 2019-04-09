<template>
    <div>
        <h1>Posts</h1>
        <ul>
            <li v-for="post in posts" :key="post.id">
                <nuxt-link :to="`/posts/${post.id}`">{{post.title}}</nuxt-link>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    async asyncData () {
        const response = await fetch('http://5cacc01b01a0b80014dcd04f.mockapi.io/posts')
        const posts = await response.json()
        return { posts }
    }
}
</script>