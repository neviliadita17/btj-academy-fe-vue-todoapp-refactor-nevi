<template>
  <div class="col-span-1 border rounded-md p-3">
    <h2 class="text-xl font-semibold mb-2">{{ title }}</h2>
    <p class="text-2xl">{{ count }}</p>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    count: Number,
  },
};
</script>
