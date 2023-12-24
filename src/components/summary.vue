<template>
  <div class="p-4 bg-white rounded-md shadow-md mb-8">
    <h1 class="text-3xl font-semibold mb-4">Todo App Summary</h1>

    <div class="grid grid-cols-4 gap-4">
      <SummaryItem title="Pending" :count="pendingTodos" />
      <SummaryItem title="Low Priority" :count="lowPriorityTodos" />
      <SummaryItem title="Medium Priority" :count="mediumPriorityTodos" />
      <SummaryItem title="High Priority" :count="highPriorityTodos" />
    </div>
  </div>
</template>

<script>
import SummaryItem from './summaryItem.vue';

export default {
  components: {
    SummaryItem,
  },
  props: {
    pendingTodos: Number,
    lowPriorityTodos: Number,
    mediumPriorityTodos: Number,
    highPriorityTodos: Number,
  },
};
</script>
