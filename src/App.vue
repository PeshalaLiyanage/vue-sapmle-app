<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
  import Header from './components/layout/Header'
  export default {
    name:'app',
    components:{
      Header
    }
  }
</script>
<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
  body{
    font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
    line-height: 1.4;
    width: 100%;
  }
  .btn{
    /*display: inline-block;*/
    border: none;
    background: #555;
    color: white;
    padding: 0.55em 2em;
    cursor: pointer;
  }
  .btn:hover{
    background: darkslategrey;
  }




</style>
