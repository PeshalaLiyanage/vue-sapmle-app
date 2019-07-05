<template>
    <div class="addTodos">
        <form>
            <input type="text" class="" v-model="title" placeholder="Add todos..">
            <input type="submit" value="Add" class="btn" @click="addTodo">
        </form>

    </div>
</template>

<script>
    // import uuid from 'uuid';
    export default {
        name: "AddTodos",
        data(){
            return{
                title:''
            }
        },
        methods:{
            addTodo(event){
                event.preventDefault();
                const newTodo = {
                    // id:uuid.v4(),
                    title: this.title,
                    completed:false
                }

                this.$emit('add-todo', newTodo);
                this.title='';
            }
        }
    }
</script>

<style scoped>
    .addTodos{
        display: inline-block;
    }
    form{
        display: flex;
    }
    input[type="text"]{
        /*padding: 0.4em 48.7em ;*/
        flex: 10;
        width: 100%;
    }
    input[type="submit"]{
        flex:2;
    }

</style>