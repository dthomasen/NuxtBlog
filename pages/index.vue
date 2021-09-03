<template>
  <div class="grid justify-items-center ml-8 mr-8">
    <div class="max-w-5xl">
      <Hero />

      <Seperator />

      <!-- <h1 class="mb-4">
        About me
      </h1>
      <div class="text-gray-800 leading-normal font-normal text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos dolorem totam a quis possimus explicabo dolorum iste consectetur, recusandae corporis quaerat veritatis error nihil assumenda repellendus maxime natus tenetur, incidunt expedita numquam veniam placeat. Fuga necessitatibus ea velit nemo repellendus quod, rerum excepturi praesentium veniam delectus quisquam quos voluptatibus facilis!
      </div>

      <Seperator />
 -->
      <h1 class="mb-4">
        Latest blog posts
      </h1>
      <BlogPostsDisplay
        :posts="posts"
      />
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const posts = await $content()
      .fetch()
      .catch((err) => {
        console.log(err)
      })
    console.log(posts)
    return {
      posts
    }
  }
}
</script>
