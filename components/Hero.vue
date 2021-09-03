<template>
  <div class="bg-gray-100 pt-16">
    <!-- container -->
    <div>
      <!-- hero wrapper -->
      <div class="grid grid-cols-1 md:grid-cols-12 gap-8 items-center">
        <!-- hero text -->
        <div class="col-span-6">
          <h1 class=" font-bold text-5xl text-gray-900 leading-tight">
            Senior Mobile Developer @ Podimo
          </h1>
          <hr class="w-12 h-1 bg-orange-500 rounded-full mt-8">
          <p class="text-gray-800 leading-relaxed mt-8 text-l font-semibold">
            A personal webpage and blog with random thoughts and tips about coding, home automation, IOT and more.
            <br /><br />
            Mostly to remind myself 😅
          </p>
        </div>

        <div class="hero-image col-span-6 place-self-center">
          <img :src="require(`@/assets/images/me.jpeg`)" alt="Photo of me" class="rounded-full h-64 w-64">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>
