<template>
  <div id="app">
      <Title msg="To Do List"/>
      <List
        :items="todos"
        @update-todo="updateTodo"
        />
      <Form @add-todo="addTodo"/>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import List from './components/List.vue'
import Form from './components/Form.vue'

export default {
  name: 'app',
  data() {
    return {
      todos: [{
        text: 'Cook dinner',
        done: false
      }, {
        text: 'Wash clothes',
        done: true
      }]
    }
  },
  methods: {
    updateTodo(i){
      this.todos[i].done = !this.todos[i].done;
    },
    addTodo(text) {
      this.todos.push({
        text,
        done: false
      })
    }
  },
  components: {
    Title,
    List,
    Form
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
