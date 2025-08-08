<template>
  <div class="p-6 min-h-screen bg-gradient-to-b from-white to-blue-50">
    <NuxtLink
      to="/"
      class="inline-flex items-center gap-1 text-blue-600 hover:text-blue-800 text-sm mb-6 transition"
    >
      ← Back to list
    </NuxtLink>

    <!-- SKELETON LOADING -->
    <div v-if="pending" class="space-y-4 animate-pulse max-w-3xl mx-auto">
      <div class="h-8 bg-blue-100 rounded w-2/3"></div>
      <div class="h-4 bg-blue-100 rounded w-full"></div>
      <div class="h-4 bg-blue-100 rounded w-11/12"></div>
      <div class="h-4 bg-blue-100 rounded w-10/12"></div>
      <div class="h-4 bg-blue-100 rounded w-9/12"></div>
    </div>

    <!-- ERROR HANDLING -->
    <div v-else-if="error || !post?.id" class="text-center text-red-600 text-lg font-medium">
      ❌ Oops! Post tidak ditemukan.
    </div>

    <!-- MAIN CONTENT -->
    <div v-else class="bg-white p-6 rounded-2xl shadow-lg border max-w-3xl mx-auto">
      <h1 class="text-3xl font-extrabold text-blue-700 mb-4 leading-snug">
        📖 {{ post.title }}
      </h1>

      <hr class="border-blue-200 mb-4" />

      <p class="text-gray-700 text-lg leading-relaxed whitespace-pre-line">
        {{ post.body }}
      </p>

      <div class="mt-8 text-sm text-gray-500 italic flex justify-between">
        <span>#{{ post.id }} • From JSONPlaceholder</span>

        <div class="flex gap-2">
          <NuxtLink
            v-if="hasPrev"
            :to="`/posts/${Number(post.id) - 1}`"
            class="text-blue-600 hover:underline"
          >
            ← Previous
          </NuxtLink>

          <NuxtLink
            v-if="hasNext"
            :to="`/posts/${Number(post.id) + 1}`"
            class="text-blue-600 hover:underline"
          >
            Next →
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const route = useRoute()
const postId = Number(route.params.id)

const { data: post, pending, error } = await useFetch(
  `https://jsonplaceholder.typicode.com/posts/${postId}`
)

const hasPrev = postId > 1
const hasNext = postId < 100 // JSONPlaceholder punya 100 post
</script>
