<template>
  <div>
    <div class="md:grid md:justify-items-center ml-8 mr-8">
      <div class="max-w-5xl">
        <BackButton />
        <div v-if="page">
          <Post
            :markdown="page"
          />
        </div>
        <div v-else>
          Post ikke fundet
        </div>
      </div>
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
  },
  methods: {
    goBack () {
      window.history.length > 1 ? this.$router.go(-1) : this.$router.push('/')
    }
  }
}
</script>

<style scoped>

</style>
