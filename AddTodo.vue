<template>
    <div class="container">
        <br>
        <h1 class="text-center">Games To Play</h1>
        <br><br>
        <form @submit="addTodo">
        <div class="form-group">
            <input required type="text" v-model="title" placeholder="title" name="title" class="form-control">
        </div>
        <div class="form-group">
            <button class="btn btn-block btn-danger">
                Add Game to Play
            </button>
        </div>
        </form>
    </div>
</template>
<script>

export default {
  name: "AddTodo",
  data(){
      return{
          title:""
      }
  },
  methods:{
      addTodo(e){
          e.preventDefault()

          const newTodo = {
              id:Date.now(),
              title:this.title,
              completed:false
          }

          this.$emit("add-todo",newTodo)

          this.title=""
      }
  }
}
</script>

<style scoped>

</style>