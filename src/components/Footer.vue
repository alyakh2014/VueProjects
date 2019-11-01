<template>
    <div>
        <ul>
            <li v-for="(task,index) in tasks" :key="index">{{task.name}}{{task.email}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Footer",
        props: ["tasks"]
    }


</script>

<style scoped>

</style>