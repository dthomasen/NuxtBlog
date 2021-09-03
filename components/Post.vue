<template>
  <div class="container mx-auto">
    <div class="ml-8">
      <h1 class="mb-2 font-bold text-5xl">
        {{ markdown.title }}
      </h1>
      <h3 class="mb-4 text-xl">
        {{ markdown.date }}
      </h3>
    </div>
    <img
      :src="require(`@/assets/images/posts/${markdown.image || 'default.jpeg'}`)"
      alt=""
      class="md:h-96 mr-8 w-full object-cover"
    />
    <nuxt-content class="m-8 prose max-w-none" :document="markdown" />
  </div>
</template>

<script>
export default {
  props: {
    markdown: Object
  }
}
</script>

<style scoped>
</style>
