<template>
  <NuxtLink class="" :to="`/posts/${post.slug}`">
    <div class="bg-white mx-auto shadow-lg rounded-lg hover:shadow-xl transition duration-200">
      <img class="rounded-t-lg" :src="require(`@/assets/images/posts/${post.image || 'default.jpeg'}`)" alt="" />
      <div class="py-4 px-8">
        <h1 class="mt-2 text-gray-900 font-bold text-2xl tracking-tight">
          {{ post.title }}
        </h1>
        <p class="py-3 text-gray-600 leading-6">
          {{ post.description }}
        </p>
      </div>
    </div>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    post: Object
  }
}
</script>

<style scoped>

</style>
