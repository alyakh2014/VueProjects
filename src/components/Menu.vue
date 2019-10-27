<template>
    <div>
        <button
                class="itemsMenu"
                v-for="(item, index) in itemsMenu"
                :key='index'
                @click="showContent(item)">{{item}}</button>
    </div>
</template>

<script>
    export default {
        name: "Menu",
        props: ['itemsMenu'],
        methods: {
            showContent(item){
                this.$emit('show-content', item);
            }
        }
    }
</script>

<style scoped>
    .itemsMenu{
        display:inline-block;
        padding: 7px 30px;
        background: #ccc;
        color: black;
    }
    .itemsMenu:not(:first-child){
        margin-left: 10px;
    }
</style>