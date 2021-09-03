<template>
  <div>
    <h1>Post</h1>
    <div v-if="page">
      <Post
        :markdown="page"
      />
    </div>
    <div v-else>
      Post ikke fundet
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const slug = params.id || 'index'
    const page = await $content(slug)
      .fetch()
      .catch((err) => {
        console.log(err)
      })
    return {
      page
    }
  }
}
</script>

<style scoped>

</style>
