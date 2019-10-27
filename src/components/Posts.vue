<template>
    <div>
        <ul>
            <li v-for="(post,index) in posts" :key="index">{{post.title}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Posts",
        props: ["posts"]
    }
</script>

<style scoped>

</style>