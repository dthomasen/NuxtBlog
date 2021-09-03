<template>
  <div class="grid lg:grid-cols-3 md:grid-cols-2 grid-cols-1 gap-12">
    <BlogPost
      v-for="post in posts"
      :key="post.title"
      :post="post"
    >
    </BlogPost>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      default: null
    }
  }
}
</script>

<style scoped>

</style>
