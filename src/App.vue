<template>
  <div id="app">
    <!--load component-->
    <Navbar2/>
    <AllFriends v-bind:friendsAll="friends" @delete="deleteFriend"/>
    <OnlineFriends v-bind:friendsOnline="friends"/>
    <Blogs/>
    <nav>
        <h2>Menu</h2>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>

    
    <img src="./assets/logo.png">
    <h1>{{ newMsg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    <p>test</p>
  </div>
</template>

<script>
//import navbar. you can choose any name instead of Navbar
import Navbar1 from './Navbar.vue'

import AllFriends from './AllFriends.vue'
import OnlineFriends from './OnlineFriends.vue'

import Blogs from './Blogs.vue'

export default {
  name: 'app',
  //register component
  components:{
    Navbar2: Navbar1, //you can again call the first Navbar whatever you want. second must be the same as the import
    OnlineFriends: OnlineFriends,
    AllFriends: AllFriends,
    Blogs
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      newMsg: 'my own msg',
      friends: [
                { name : 'name1', online : true },
                { name : 'name2', online : false },
                { name : 'name3', online : true },
                { name : 'name4', online : false }
            ]
    }
  },
  methods:{
    deleteFriend(payload){
      console.log(payload)
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
  color: red;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
