
<template>
  <div class="container">
    <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
      <p>
        <input
          type="checkbox"
          v-on:change="markComplete"
          v-bind:checked="todo.completed"
        />
        {{ todo.title }}
         
        <button  class="del" @click="$emit('delete-todo', todo.id)">x</button>
      </p>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],  
  data() {
    return {
      todoLocal: this.todo,
    }
  },
  methods: {
    markComplete() {
      this.todoLocal.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  margin: 20px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}

.update {
  background: blue;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>