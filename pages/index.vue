<template>
  <div class="index-page pt-10">
    <carousel />
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
