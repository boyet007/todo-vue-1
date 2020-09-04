<template>
  <div id="app">
 
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
       <AddTodo v-on:add-todo="addTodo"/>
    </div>
</template>

<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
export default {
  name: 'App',
  components: { Todos, AddTodo },
  data() {
    return {
      todos: [
        { id: 1, title: 'Go workout', completed: false },
        { id: 2, title: 'Eat Fish', completed: false },
        { id: 3, title: 'Study English', completed: false },
        { id: 4, title: 'Clean the dishes', completed: false },
        { id: 5, title: 'Teethbrush', completed: false },
        { id: 6, title: 'Sleep', completed: false },
      ]
    }
  },
  methods: {
    addTodo(newTodoObj) {
        this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      debugger;
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
}

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

