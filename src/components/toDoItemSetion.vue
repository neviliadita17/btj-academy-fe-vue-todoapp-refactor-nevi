<template>
  <div class="w-1/2">
    <h3 class="text-lg font-semibold mb-2">{{ title }}</h3>
    <div v-if="items.length === 0" class="text-gray-500">No {{ title.toLowerCase() }}s yet.</div>
    <div v-for="item in items" :key="item.id" class="bg-white p-4 mb-4 rounded-md shadow-md">
      <!-- ... -->
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    items: Array,
  },
};
</script>
