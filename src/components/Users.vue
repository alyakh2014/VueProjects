<template>
    <div>
        <ul>
            <li v-for="(user,index) in users"
                :key="index"
                @click="deleteUser(index)"
            >{{user.name}}:{{user.email}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Users",
        props: ["users"],
        methods:{
            deleteUser(index){
                this.$emit('delete-user', index);
            }
        }
    }
</script>

<style scoped>

</style>