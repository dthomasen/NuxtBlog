<template>
  <button class="lg:-mx-16 mt-8 mb-8 grid grid-cols-2 bg-orange-400 px-5 py-3 text-sm shadow-sm font-medium tracking-wider  text-orange-100 rounded-full hover:shadow-2xl hover:bg-orange-500" @click="goBack()">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
    </svg>
    <p class="pt-0.5">
      Back
    </p>
  </button>
</template>

<script>
export default {
  methods: {
    goBack () {
      window.history.length > 1 ? this.$router.go(-1) : this.$router.push('/')
    }
  }
}
</script>

<style scoped>

</style>
