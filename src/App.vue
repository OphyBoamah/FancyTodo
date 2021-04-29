<template>
  <div class="main">
    <h1>My Todo List</h1>
    <form @submit.prevent="addNewTodo">
      <input type="text" placeholder="Enter a todo here" v-model="newTodo">
      <button type="submit">Save</button>
    </form>
  <div class="todos" v-for="todo in todos" :key="todo.id">
    <p>{{todo.task}}</p>
  </div>
    {{newTodo.task}}
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      newTodo:"",
      newId:6,
      todos : [
        {
          id:1,
          task:"Wake up"
        },
        {
          id:2,
          task:"Have morning devotion"
        },
        {
          id:3,
          task:"Perform house chores"
        },
        {
          id:4,
          task:"Have breakfast"
        },
        {
          id:5,
          task:"Read a book"
        },
      ]
    }
  },
  methods: {
    addNewTodo() {
      this.todos.push({id:this.newId, task:this.newTodo})
          this.newTodo = ""
          this.newId++

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


<!--<form @submit.prevent="addNewTodo">-->
<!--<input type="text" placeholder="Enter a todo" v-model="newTodo">-->
<!--<button type="submit">Save</button>-->
<!--</form>-->
<!--<div id="todos" v-for="todo in todos" :key="todo.id">-->
<!--{{todo.task}}-->
<!--</div>-->