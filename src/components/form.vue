<!-- Form.vue -->
<template>
    <div class="p-4 bg-white rounded-md shadow-md mb-8">
      <h2 class="text-2xl font-semibold mb-4">Add Todo</h2>
      <form v-on:submit.prevent="addTodo">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
          <div>
            <label for="name" class="block text-sm font-medium text-gray-700">Name:</label>
            <input v-model="newTodo.name" type="text" id="name" name="name" required class="mt-1 p-2 w-full border rounded-md" />
          </div>
          <div>
            <label for="priority" class="block text-sm font-medium text-gray-700">Priority:</label>
            <select v-model="newTodo.priority" id="priority" name="priority" class="mt-1 p-2 w-full border rounded-md">
              <option value="low">Low</option>
              <option value="medium">Medium</option>
              <option value="high">High</option>
            </select>
          </div>
        </div>
        <div class="flex justify-end mt-4">
          <button type="submit" :disabled="!newTodo.name" class="bg-green-500 text-white px-4 py-2 rounded-md hover:bg-green-600 focus:outline-none -right">
            Save
          </button>
        </div>
      </form>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        newTodo: {
          name: '',
          priority: 'low',
        },
      };
    },
    methods: {
      addTodo() {
        if (this.newTodo.name) {
          this.$emit('addTodo', { ...this.newTodo });
          this.newTodo.name = '';
          this.newTodo.priority = 'low';
        }
      },
    },
};
</script>
  
  <style scoped>
  </style>
  