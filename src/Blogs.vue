<template>
    <div class="blogs">
        <h2>{{ blogTitle }}</h2>
        <input type="text" v-model="searchTerm">
        <button v-on:click="changeTitle">change title</button>
        <div v-for="post in filteredPosts" :key="post.id">
            <h3> {{ post.title }} </h3>
            <p> {{ post.body | filterSnippet }} </p>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'Blogs',

    data(){
        return{
            blogTitle: 'Blogs',
            posts: [],
            searchTerm: ''
        }
    },
    methods:{
        changeTitle(){
            this.blogTitle = 'new title'
        }
    },
    computed:{
        filteredPosts(){
            return this.posts.filter(post => {
                return post.title.match(this.searchTerm)
            })
        }
    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts/')
        .then(response => {
            console.log(response)
            this.posts = response.data
        }).catch(error => {
            console.log(error)
        })
    }
    /*
    beforeCreate(){
        alert('before create hook')
    },
    created(){
        alert('created hook')
    },
    beforeUpdate(){
        alert('before update hook')
    }
    */
}
</script>