<template>
  <div class="index-page">
    <div class="px-5">
      <carousel />
    </div>
  </div>
</template>

<script>
import carousel from "~/components/index/carousel.vue";
export default {
  components: {
    carousel
  }
};
</script>

<style scoped>
.index-page {
  overflow-x: hidden;
}
</style>
