<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <Navbar></Navbar>
    <Friends :friends="friendlist" @delete="deleteFriend"></Friends>
    <ActiveFriends :friends="friendlist"></ActiveFriends>
    <Hook></Hook>
    
  
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Friends from './components/Friends.vue'
import ActiveFriends from './components/ActiveFriends.vue'
import Hook from './components/Hook.vue'


export default {
  name: 'App',
  data(){
    return{
      title:'Hi everyone.How are you doing?',
       friendlist:[
               
                 {name:'kalam',active:true},
                 
                 {name:'mamun',active:false}
                
           ]
    }
  },
  components:{
    Navbar,
    Friends,
    ActiveFriends,
    Hook
  },
  methods:{
    deleteFriend(payload){
     this.friendlist=this.friendlist.filter(friend =>{
        return friend.name !== payload.name
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
