<template>
<div id="friends">
<h2>Friends</h2>
<div v-for="(friend,index) in friends" :key="index">
   <h6 @click="unfriend(friend.name)"> {{friend.name}}</h6>

</div>
</div>
    
</template>
<script>
export default {
    name:'Friends',
    props:['friends'],
    data(){
        return{
         
        }
    },
    methods:{
        unfriend(name){
            this.$emit('delete',{name})
        }
    }
    
}
</script>
<style>

h6{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 
}


</style>