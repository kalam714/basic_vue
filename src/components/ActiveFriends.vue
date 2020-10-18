<template>
<div id="active">
    <h2>Active Friends</h2>
<div v-for="(friend,index) in friends" :key="index">
   <h6 v-if="friend.active"> {{friend.name}}</h6>

</div>

 </div>   
</template>
<script>
export default {
    name:'ActiveFriends',
    props:['friends'],
   data(){
        return{
         
        }
    }
    
}
</script>
<style>


</style>