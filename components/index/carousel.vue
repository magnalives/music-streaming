<template>
  <div>
    <div class="float-right my-3">
      <button
        @click="previousCarousel"
        class="px-3 py-2 bg-gray-700 text-white select-none"
      >
        <img src="/icons/arrow-left.svg" alt="" />
      </button>
      <button
        @click="nextCarousel"
        class="px-3 py-2 bg-gray-700 text-white mr-3"
      >
        <img src="/icons/arrow-right.svg" alt="" />
      </button>
    </div>
    <div
      class=" flex overflow-x-hidden carousel-container"
      v-bind:style="{
        transform: 'translate3d(' + carouselx + '0px, 0px, 0px)'
      }"
      id="swipeguesture"
    >
      <div v-for="n in 10" :key="n">
        <div class="pr-5">
          <div
            class="bg-gray-500 bg-center bg-cover rounded-lg carousel-img shadow-lg flex"
            v-bind:style="{ backgroundImage: 'url(' + image + ')' }"
          >
            <div
              class=" w-full flex"
              @mouseenter="playHover"
              @mouseleave="playHoverOut"
            >
              <img
                class="m-auto hidden"
                src="/icons/play.svg"
                alt=""
                srcset=""
              />
            </div>
          </div>
          <div class="text-md font-bold text-dark-blue pt-2 select-none">
            Lorde-Melodrama
          </div>
          <div class="text-md font-bold text-light-blue select-none">
            Pop Music
          </div>
        </div>
      </div>
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
    },
    playHover(e) {
      e.srcElement.classList.toggle("carousel-overlay");
      e.srcElement.childNodes[0].style.display = "block";
    },
    playHoverOut(e) {
      e.srcElement.classList.toggle("carousel-overlay");
      e.srcElement.childNodes[0].style.display = "none";
    },
    playMusic() {
      console.log("music played");
    }
  },
  mounted() {}
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
.carousel-overlay {
  background: linear-gradient(0deg, #485df7, transparent);
}
</style>
