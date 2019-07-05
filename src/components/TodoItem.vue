<template>
    <div class="todoItem" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
    export default {
        name:"TodoItem",
        props:["todo"],
        methods:{
            markComplete(){
                console.log('markComplete method called');
                this.todo.completed = !this.todo.completed;
            }
        }
    }
</script>

<style scoped>

    .todoItem{
        background: gainsboro;
        padding: 1em;
        border-bottom: 1px #ccc dotted;
    }
    .is-complete{
        text-decoration: line-through;
    }

    .del{
        padding:5px 9px;
        background-color: red;
        color: white;
        border-radius: 50%;
        float:right;
        cursor: pointer;
    }

</style>