<template>
  <div>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-on:delete-todo="deleteTodo" v-bind:todos="todos"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  data(){
    return {
      todos:[
        {
          id:1,
          title:"God of War",
          completed:true
        },
        {
          id:2,
          title:"Monkey Island",
          completed:false
        },
        {
          id:3,
          title:"Tetris",
          completed:false
        },
        {
          id:4,
          title:"Valorant",
          completed:false
        },
        {
          id:5,
          title:"DOOM",
          completed:true
        }
      ]
    }
  },
  components: {
    Todos,
    AddTodo
  },
  methods:{
    addTodo(todo){
      this.todos=[...this.todos,todo]
    },
    deleteTodo(id){
      this.todos = this.todos.filter((todo) => todo.id !== id)

    }
  }
}
</script>