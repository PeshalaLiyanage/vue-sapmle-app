<template>
    <div class="header">
        <h1>TodoList</h1>
        <div id="nav" >
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style>
    .header{
        text-align: center;
        background-color: darkslategrey ;
        color: white;

    }
    a{
        color: white;
        text-decoration: none;
    }

</style>