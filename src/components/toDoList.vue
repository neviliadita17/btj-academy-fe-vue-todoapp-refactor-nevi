<!-- ToDoList.vue -->
<template>
    <div class="p-4 bg-white rounded-md shadow-md">
      <h2 class="text-2xl font-semibold mb-4">Todo List</h2>
      <div class="flex space-x-4">
        <div class="w-1/2">
          <h3 class="text-lg font-semibold mb-2">Todo</h3>
          <div v-if="todos.length === 0" class="text-gray-500">No todos yet.</div>
          <ToDoItem v-for="todo in todos" :key="todo.id" :todo="todo" @deleteTodo="deleteTodo" @markDone="markDone" />
        </div>
        <div class="w-1/2">
          <h3 class="text-lg font-semibold mb-2">Done</h3>
          <div v-if="doneTodos.length === 0" class="text-gray-500">No completed todos yet.</div>
          <DoneItem v-for="doneTodo in doneTodos" :key="doneTodo.id" :doneTodo="doneTodo" />
        </div>
      </div>
    </div>
</template>
  
<script>
  import ToDoItem from './toDoItem.vue';
  import DoneItem from './doneItem.vue';
  
  export default {
    components: {
      ToDoItem,
      DoneItem,
    },
    props: {
      todos: Array,
      doneTodos: Array,
    },
    methods: {
      deleteTodo(id) {
        this.$emit('deleteTodo', id);
      },
      markDone(id) {
        this.$emit('markDone', id);
      },
    },
  };
</script>
  
  <style scoped>
  </style>
  