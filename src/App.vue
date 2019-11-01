<template>
  <div id="app">
    <Menu v-bind:itemsMenu="itemsMenu" @show-content="showContent"/>
    <Users :users="users" @delete-user="deleteUser"/>
    <Posts :posts="posts"/>
    <Footer :tasks="tasks"/>
  </div>
</template>

<script>
import Menu from './components/Menu.vue';
import Users from './components/Users.vue';
import Posts from './components/Posts.vue';
import Footer from "./components/Footer";
import axios from 'axios';

export default {
  name: 'app',
  data(){
    return{
      itemsMenu: ["Users", "Posts"],
      users: [],
      posts: [],
      tasks: []
    }
  },
  components: {
    Menu,
    Users,
    Posts,
    Footer
  },
  methods:{
    showContent(item) {
      this.users = [];
      this.posts = [];
      // eslint-disable-next-line no-undef
      axios
         .get('http://jsonplaceholder.typicode.com/'+item+'/')
         .then(response => (
                 this[item.toLowerCase()] = response.data
         ))
         .catch(error => alert(error));
      },
      deleteUser(index){
        this.users.splice(index, 1);
      },
  },
  mounted() {
    axios
            .get('http://jsonplaceholder.typicode.com/users/')
            .then(response => (
                    this.tasks = response.data
            ))
            .catch(error => alert(error));
  }
}
</script>

<style>
#app {

}
</style>
