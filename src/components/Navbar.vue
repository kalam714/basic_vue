<template>
<nav>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Post</a></li>
        <li><a href="#">About</a></li>

    </ul>
</nav>
    
</template>
<script>
export default {
    name:'Navbar',
    data(){
        return{

        }
    }
    
}
</script>
<style>
nav {
    text-align: center;
}
nav ul{
    padding:0px;
}
nav li{
    display: inline-block;
    list-style-type: block;
    margin: 0px;
    padding:10px;
}

</style>