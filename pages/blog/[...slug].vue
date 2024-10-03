<template>
  <article>
    <h1 class="text-4xl font-bold mb-4">{{ post.title }}</h1>
    <p class="text-gray-600 mb-8">{{ formatDate(post.date) }}</p>
    <ContentRenderer :value="post" />
  </article>
</template>

<script setup>
const { path } = useRoute()
const { data: post } = await useAsyncData(`content-${path}`, () => queryContent(path).findOne())

if (!post.value) {
  throw createError({ statusCode: 404, message: 'Post not found' })
}

const formatDate = (date) => {
  return new Date(date).toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' })
}
</script>