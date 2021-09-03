<template>
  <div class="grid lg:grid-cols-3 md:grid-cols-2 grid-cols-1 gap-12">
    <BlogPost
      v-for="item in 10"
      :key="item"
    >
    </BlogPost>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>
