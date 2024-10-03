<template>
  <div>
    <h1 class="text-3xl font-bold mb-8">Latest Posts</h1>
    <div v-for="post in posts" :key="post._path" class="mb-8">
      <h2 class="text-2xl font-semibold mb-2">
        <NuxtLink :to="post._path" class="text-blue-600 hover:underline">
          {{ post.title }}
        </NuxtLink>
      </h2>
      <p class="text-gray-600">{{ post.description }}</p>
    </div>
  </div>
</template>

<script setup>
const { data: posts } = await useAsyncData('posts', () => queryContent('/blog').sort({ date: -1 }).limit(5).find())
</script>