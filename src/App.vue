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
            <input type="text" v-model="todo.descripion" name="" id="" class="form-input" placeholder="New task">
            <button class="btn btn-primary input-group-btn">
              {{ btnText }}&nbsp;
              <i class="icon icon-plus" />
            </button>
          </div>
        </form>
        <div class="todo-list">
          <div v-for="t in todos" :key="t.id" class="line-task">
            <div class="tile">
              <div class="tile-icon">
                <span class="d-flex">
                  <i class="icon icon-time centered" />
                </span>
              </div>
              <div class="tile-content">
                <p class="tile-subtitle">{{ t.descripion }}</p>
              </div>
              <div class="tile-action">
                <button class="btn btn-link">
                  <i class="icon icon-check"/>
                </button>
                <button class="btn btn-link">
                  <i class="icon icon-delete"/>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

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
  methods: {
    addTodo(todo) {
      todo.id = Date.now()
      this.todos.push(todo)
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

.todo-list .tile {  
  align-items: center;
}

.todo-list p {
  margin-bottom: 0;
}

.todo-list i:not(icon-delete) {
  color: #4341d4;
}

.todo-list i.icon-delete {
  color: red;
}

</style>