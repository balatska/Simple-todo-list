<template>
  <div id="app">
    <h1>TODO LIST</h1>
    <AddTodo 
      @add-todo="addTodo"
    />
    <TodoList 
      v-bind:todos="todos"
      v-on:remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'
export default {
  name: 'app',
  data() {
    return {
      todos: [
        {id: 1, title: 'one', completed: false},
        {id: 2, title: 'two', completed: false},
        {id: 3, title: 'three', completed: false},
      ]
    }
  },
  components: {
    TodoList, AddTodo
  },
  methods: {
    removeTodo (id) {
      this.todos = this.todos.filter(t => t.id !==id)
    },

    addTodo(todo) {
      this.todos.push(todo)
    }
  }
}
</script>

<style lang="scss">

</style>
