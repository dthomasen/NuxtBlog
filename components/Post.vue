<template>
  <div class="container mx-auto">
    <h1>{{ markdown.title }}</h1>
    <h3>{{ markdown.date }}</h3>
    <img
      :src="require(`@/assets/images/posts/${markdown.image}`)"
      alt=""
      class="image"
    >
    <nuxt-content :document="markdown" />
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
