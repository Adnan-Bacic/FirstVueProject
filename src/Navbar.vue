<template>
    <nav>
        <h2>Menu</h2>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
</template>

<script>
    export default{
        //name for object
        name: 'Navbar',
        //data function
        data(){
            //returns an object
            return{

            }
        }
    }
</script>

<style scoped>
    h2{
        color: purple;
    }
    a{
        color: blue;
    }
    nav{
        text-align: center;
    }
    nav ul{
        padding: 0;
    }
    nav li{
        display: inline-block;
        list-style: none;
        margin: 0;
    }
</style>