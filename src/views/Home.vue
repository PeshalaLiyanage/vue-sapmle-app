<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos = "todos" v-on:del-todo="delTodo"/>
  </div>
</template>

<script>
  import AddTodo from '../components/AddTodos';
  import Todos from '../components/Todos';
  import axios from 'axios';
  export default {
    name: 'Home',
    components: {
      Todos,
      AddTodo
    },
    data(){
      return{
        todos:[]
      }
    },
    methods:{
      delTodo(id){
        axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
                .then(res => this.todos = this.todos.filter(todo => todo.id !== id))


      },
      addTodo(newTodo){
        const {title, completed} = newTodo;
        axios.post('https://jsonplaceholder.typicode.com/todos',{
          title,
          completed
        })
                .then(res => this.todos=[...this.todos,res.data] )
                .catch(err => console.log(err))

      },
    },
    created(){
      axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
              .then(res => this.todos = res.data)
              .catch(err => console.log(err))
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