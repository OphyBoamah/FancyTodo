<template>
  <div class="main">
    <h1>My Todo List</h1>
    <div id="canvas">
      <form @submit.prevent="addNewTodo">
        <input class="todo-input" type="text" placeholder="Enter a todo here" v-model="newTodo">
        <button class="todo-button" type="submit">Save</button>
      </form>
      <div class="todos" v-for="todo in todos" :key="todo.id">
        <p>{{todo.task}}</p>
        <div class="icons">
          <p class="icon icon-1"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M9 2a1 1 0 00-.894.553L7.382 4H4a1 1 0 000 2v10a2 2 0 002 2h8a2 2 0 002-2V6a1 1 0 100-2h-3.382l-.724-1.447A1 1 0 0011 2H9zM7 8a1 1 0 012 0v6a1 1 0 11-2 0V8zm5-1a1 1 0 00-1 1v6a1 1 0 102 0V8a1 1 0 00-1-1z" clip-rule="evenodd" />
          </svg>
          </p>
          <p class="icon icon-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path d="M17.414 2.586a2 2 0 00-2.828 0L7 10.172V13h2.828l7.586-7.586a2 2 0 000-2.828z" />
              <path fill-rule="evenodd" d="M2 6a2 2 0 012-2h4a1 1 0 010 2H4v10h10v-4a1 1 0 112 0v4a2 2 0 01-2 2H4a2 2 0 01-2-2V6z" clip-rule="evenodd" />
            </svg>
          </p>
          <p class="icon icon-3">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
          </p>
          <p class="icon icon-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
              <path d="M10 12a2 2 0 100-4 2 2 0 000 4z" />
              <path fill-rule="evenodd" d="M.458 10C1.732 5.943 5.522 3 10 3s8.268 2.943 9.542 7c-1.274 4.057-5.064 7-9.542 7S1.732 14.057.458 10zM14 10a4 4 0 11-8 0 4 4 0 018 0z" clip-rule="evenodd" />
            </svg>
          </p>
        </div>
      </div>
    </div>
<!--    {{newTodo.task}}-->
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
  width: 100%;
}
#canvas {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.todos {
  width: 50%;
  text-align: center;
  display: flex;
  /*flex-direction: column;*/
  justify-content: space-between;
  align-items: center;
}
.todo-input {
  padding: 10px 30px;
}

.todo-button {
  padding: 10px 15px;
  background: #42b983;
  color: #fff;
  border-radius: 5px;
  border: none;
  margin-left: 20px;
}

.todo-button:hover {
  background: #247553;
}

.icon {
  width: 15px;
}
.icon-1 {
  color: red;
}
.icon-2 {
  color: dodgerblue;
}
.icon-3 {
  color: green;
}
.icon-4 {
  color: coral;
}
.icons {
  display: flex;
}
</style>


<!--<form @submit.prevent="addNewTodo">-->
<!--<input type="text" placeholder="Enter a todo" v-model="newTodo">-->
<!--<button type="submit">Save</button>-->
<!--</form>-->
<!--<div id="todos" v-for="todo in todos" :key="todo.id">-->
<!--{{todo.task}}-->
<!--</div>-->