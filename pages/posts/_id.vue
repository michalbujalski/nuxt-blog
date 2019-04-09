<template>
    <div>
        <h1>{{post.title}}</h1>
        <p>{{post.description}}</p>
    </div>
</template>
<script>
export default {
    async asyncData ({params}) {
        const response = await fetch(`http://5cacc01b01a0b80014dcd04f.mockapi.io/posts/${params.id}`)
        const post = await response.json()
        return { post }
    }
}
</script>