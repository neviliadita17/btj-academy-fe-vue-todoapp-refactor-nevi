<!-- ToDoItem.vue -->
<template>
    <div class="bg-white p-4 mb-4 rounded-md shadow-md">
      <div class="flex justify-between items-center mb-2">
        <div>
          <p class="text-xl font-semibold">{{ todo.name }}</p>
          <div class="mt-1 flex items-center">
            <span class="text-sm font-medium text-gray-500">Priority:</span>
            <span
              v-bind:class="{
                'bg-blue-500': todo.priority === 'low',
                'bg-yellow-500': todo.priority === 'medium',
                'bg-red-500': todo.priority === 'high',
              }"
              class="ml-2 w-4 h-4 rounded-full inline-block"
            ></span>
            <span class="ml-2">{{ todo.priority.charAt(0).toUpperCase() + todo.priority.slice(1) }}</span>
          </div>
        </div>
        <div class="flex flex-col space-y-2 sm:flex-row sm:space-x-2 sm:space-y-0">
          <button @click="deleteTodo" class="px-4 py-2 rounded-md bg-red-500 text-white sm:px-2 sm:py-1 md:px-3 md:py-2 lg:px-4 lg:py-2">
            Delete
          </button>
          <button @click="markDone" class="px-4 py-2 rounded-md bg-green-500 text-white sm:px-2 sm:py-1 md:px-3 md:py-2 lg:px-4 lg:py-2">
            Done
          </button>
        </div>
      </div>
    </div>
</template>
  
<script>
  export default {
    props: {
      todo: Object,
    },
    methods: {
      deleteTodo() {
        this.$emit('deleteTodo', this.todo.id);
      },
      markDone() {
        this.$emit('markDone', this.todo.id);
      },
    },
  };
</script>
  
  <style scoped>
  </style>
  