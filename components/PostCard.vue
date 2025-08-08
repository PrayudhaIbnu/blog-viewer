<template>
  <NuxtLink
    :to="`/posts/${id}`"
    class="block p-5 bg-white rounded-2xl shadow-lg border hover:shadow-2xl hover:bg-blue-50 transition-all duration-300 hover:scale-[1.03] group"
  >
    <div class="flex justify-between items-start gap-2 mb-3">
      <h2
        class="text-xl font-bold text-blue-700 group-hover:text-blue-900 transition line-clamp-2"
      >
        {{ title }}
      </h2>
      <span
        class="text-sm font-semibold bg-blue-100 text-blue-700 px-3 py-1 rounded-full shadow-sm"
      >
        #{{ id }}
      </span>
    </div>

    <p
      class="text-gray-600 group-hover:text-gray-800 text-sm leading-relaxed line-clamp-3"
    >
      {{ body }}
    </p>

    <div class="mt-4 text-right text-xs text-blue-500 group-hover:text-blue-700 italic">
      Click to read →
    </div>
  </NuxtLink>
</template>

<script setup>
defineProps({
  id: Number,
  title: String,
  body: String,
});
</script>
