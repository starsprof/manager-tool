<template>
  <div class="list-cards">
    <TodoListItem v-for="todo in todos" :key="todo.id" :todo="todo" @remove="removeTodo"/>
    <AddTodoListItem v-model="newTodoText" @keydown.enter="addTodo"/>
  </div>
</template>

<script>
import TodoListItem from './TodoListItem'
import AddTodoListItem from './AddTodoListItem'
let nextTodoId = 1
export default {
  name: 'TodoList',
  data: function () {
    return {
      newTodoText: '',
      todos: [
        {
          id: nextTodoId++,
          title: 'Задача 1'
        },
        {
          id: nextTodoId++,
          title: 'Задача 2'
        },
        {
          id: nextTodoId++,
          title: 'Задача 3'
        }
      ]
    }
  },
  methods: {
    addTodo () {
      const trimmedText = this.newTodoText.trim()
      if (trimmedText) {
        this.todos.push({
          id: nextTodoId++,
          title: trimmedText
        })
        this.newTodoText = ''
      }
    },
    removeTodo (idToRemove) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== idToRemove
      })
    }
  },
  components: { AddTodoListItem, TodoListItem }
}
</script>

<style scoped>
  .list-cards {
    flex: 1 1 auto;
    margin-bottom: 0;
    overflow-y: auto;
    overflow-x: hidden;
    margin: 0 4px;
    padding: 0 4px;
    z-index: 1;
    min-height: 0;
  }
  .open-card-composer {
    border-radius: 0 0 3px 3px;
    color: #5e6c84;
    display: block;
    flex: 0 0 auto;
    padding: 8px;
    position: relative;
    text-decoration: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

</style>
