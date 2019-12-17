<template>
  <div>
    <div
      class=" flex overflow-x-hidden carousel-container"
      v-bind:style="{
        transform: 'translate3d(' + carouselx + '0px, 0px, 0px)'
      }"
    >
      <div v-for="n in 10" :key="n">
        <div class="pr-5">
          <div
            class="bg-gray-500 bg-center bg-cover rounded-lg carousel-img shadow-lg"
            v-bind:style="{ backgroundImage: 'url(' + image + ')' }"
          ></div>
          <div class="text-md font-bold text-dark-blue pt-2">
            Lorde-Melodrama
          </div>
          <div class="text-md font-bold text-light-blue ">Pop Music</div>
        </div>
      </div>
    </div>
    <div class="mt-5">
      <button
        @click="previousCarousel"
        class="px-3 py-2 bg-gray-700 text-white"
      >
        Previous
      </button>
      <button
        @click="nextCarousel"
        class="px-3 py-2 bg-gray-700 text-white mr-3"
      >
        Next
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      image: "/img/album-cover.jpg",
      carouselx: 0
    };
  },
  methods: {
    nextCarousel() {
      this.carouselx = this.carouselx - 40;
    },
    previousCarousel() {
      this.carouselx = this.carouselx + 40;
    }
  }
};
</script>

<style scoped>
.carousel-img {
  width: 180px;
  height: 180px;
}
.carousel-container {
  transition: all 1s ease 0s;
  width: 2000px;
}
</style>
