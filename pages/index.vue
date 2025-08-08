<template>
  <div class="p-6 min-h-screen bg-gradient-to-b from-white to-blue-50">
    <div class="text-center mb-10">
      <h1 class="text-4xl font-extrabold text-blue-700 mb-2">
        📚 Blog Viewer
      </h1>
      <p class="text-gray-600 text-sm">Baca artikel random dari JSONPlaceholder API 👇</p>
    </div>

    <div v-if="pending" class="flex justify-center items-center h-40 text-blue-600 text-lg animate-pulse">
      Loading articles...
    </div>

    <div
      v-else
      class="grid gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4"
    >
      <PostCard
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        :body="post.body"
        :id="post.id"
      />
    </div>
  </div>
</template>

<script setup>
const { data: posts, pending } = await useFetch('https://jsonplaceholder.typicode.com/posts')
</script>
