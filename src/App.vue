<template>
  <div id="app">    
    <div class="container grid-xs">
      <div class="logo-content ">
        <img src="@/assets/logo.png" alt="Logo do Vue" class="img-responsive logo p-centered">
      </div>
      <div class="form">
        <div class="form-header">
          <h2>
            {{ title }}
            <i class="icon icon-caret"></i>
          </h2>
        </div>
        <form @submit.prevent="addTodo(todo)">
          <div class="input-group">
            <input type="text" v-model="todo.description" name="" id="" class="form-input" placeholder="New task">
            <button class="btn btn-primary input-group-btn">
              {{ btnText }}&nbsp;
              <i class="icon icon-plus" />
            </button>
          </div>
        </form>
        <div class="todo-list">
          <todo v-for="{id, todo} in todos" :key="id" :todo="todo" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import Todo from './components/toDo'


export default {
  name: 'app',
  data () {
    return {
      title: 'ToDo List',
      btnText: 'Add',
      todos: [],
      todo: {
        checked: false
      }
    }
  },
  components: {
    Todo
  },
  methods: {
    addTodo(todo) {
      const response = {
        id: Date.now(),
        todo
      }
      this.todos.push(response)
      this.todo = {checked: false}
      console.log(this.todo)
    }
  }
}
</script>

<style scoped>

.logo {
  max-width: 125px;
  margin: 0 auto;
}
.form-header h2 {
  display: flex;
  align-items: center;
  color: #4341d4;
}

.todo-list {
  padding-top: 2rem;
}
</style>