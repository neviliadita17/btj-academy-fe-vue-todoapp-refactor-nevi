<!-- App.vue -->
<template>
  <div class="flex flex-col items-center justify-center p-8 bg-gray-100 min-h-screen">
    <div class="max-w-4xl mx-auto p-5 bg-white shadow-md rounded-md">
      <Summary
        :pendingTodos="pendingTodos"
        :lowPriorityTodos="lowPriorityTodos"
        :mediumPriorityTodos="mediumPriorityTodos"
        :highPriorityTodos="highPriorityTodos"
      />

      <Form @addTodo="addTodo" />

      <ToDoList :todos="todos" :doneTodos="doneTodos" @deleteTodo="deleteTodo" @markDone="markDone" />
    </div>
  </div>
</template>

<script>
import Summary from './components/summary.vue';
import Form from './components/form.vue';
import ToDoList from './components/toDoList.vue';

export default {
  data() {
    return {
      todos: JSON.parse(localStorage.getItem('todos')) || [],
      doneTodos: JSON.parse(localStorage.getItem('doneTodos')) || [],
      newTodo: {
        name: '',
        priority: 'low',
      },
    };
  },
  computed: {
    pendingTodos() {
      return this.todos.filter((todo) => !todo.completed).length;
    },
    lowPriorityTodos() {
      return this.todos.filter((todo) => todo.priority === 'low').length;
    },
    mediumPriorityTodos() {
      return this.todos.filter((todo) => todo.priority === 'medium').length;
    },
    highPriorityTodos() {
      return this.todos.filter((todo) => todo.priority === 'high').length;
    },
  },
  methods: {
    addTodo(newTodo) {
      newTodo.id = this.todos.length + 1;
      this.todos.push(newTodo);
      localStorage.setItem('todos', JSON.stringify(this.todos));
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
      localStorage.setItem('todos', JSON.stringify(this.todos));
    },
    markDone(id) {
      const todoIndex = this.todos.findIndex((todo) => todo.id === id);
      if (todoIndex !== -1) {
        const doneTodo = this.todos.splice(todoIndex, 1)[0];
        this.doneTodos.push(doneTodo);
        localStorage.setItem('todos', JSON.stringify(this.todos));
        localStorage.setItem('doneTodos', JSON.stringify(this.doneTodos));
      }
    },
  },
  components: {
    Summary,
    Form,
    ToDoList,
  },
};
</script>

<style scoped>
</style>
