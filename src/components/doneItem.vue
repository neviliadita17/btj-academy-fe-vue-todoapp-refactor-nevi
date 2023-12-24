<!-- DoneItem.vue -->
<template>
    <div class="bg-white p-4 mb-4 rounded-md shadow-md">
      <div>
        <p class="text-xl font-semibold">{{ doneTodo.name }}</p>
        <div class="mt-1 flex items-center">
          <span class="text-sm font-medium text-gray-500">Priority:</span>
          <span
            v-bind:class="{
              'bg-blue-500': doneTodo.priority === 'low',
              'bg-yellow-500': doneTodo.priority === 'medium',
              'bg-red-500': doneTodo.priority === 'high',
            }"
            class="ml-2 w-4 h-4 rounded-full inline-block"
          ></span>
          <span class="ml-2">{{ doneTodo.priority.charAt(0).toUpperCase() + doneTodo.priority.slice(1) }}</span>
        </div>
      </div>
    </div>
</template>
  
<script>
  export default {
    props: {
      doneTodo: Object,
    },
  };
</script>
  
<style scoped>
</style>
  