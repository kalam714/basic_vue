<template>
<div>
<h2>{{title}}</h2>
<button @click="updateText">Update</button>
<h1>Posts</h1><hr>
<input type="text"  v-mode="searchTerm"  placeholder="Search">
<div v-for="post in filterSearch" :key="post.id"> 
    <h2>{{post.title}}</h2>
    <p>{{post.body | short }}</p>
    

</div>
</div>

</template>

<script>
import axios from 'axios'
export default {
    name:'Hook',
    
   data(){
        return{
         title:'Used Hook lifeCyle',
         posts:[],
         searchTerm: ''
    }
    },
    computed:{
        filterSearch(){
            return this.posts.filter(post =>{
                return post.title.match(this.searchTerm)
            })
        }

    },
    methods:{
        updateText(){
            this.title='Text Updated Successfully.'
            
        }
    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response =>{
            this.posts=response.data
        })
        .catch(error =>{
            console.log(error)
        })

    },
   

    
}
</script>
<style>
h1{
    color: brown;
    text-align: center;
}


</style>