<template>
  <div>
    <div class="bg-white w-full py-5 flex fixed top-0">
      <button @click="switchNav" class="focus:outline-none">
        <div class="ml-5">
          <img src="/icons/menu.svg" alt="" />
        </div>
      </button>

      <nuxt-link to="/">
        <img class="ml-10" src="/icons/pixitone.svg" alt="pixitone logo" />
      </nuxt-link>
    </div>
    <div id="navSlider" class="h-screen fixed top-0 transition-small">
      <div id="navdrawer" class="relative w-drawer">
        <div class="mt-5">
          <AppNav />
          <div class=" w-full bottom-0">
            <button
              id="collapse-menu"
              class="fixed bottom-0 focus:outline-none"
              @click="minNav"
            >
              <div
                class="py-3 flex justify-center items-center nav-list bg-gray-800"
              >
                <img
                  id="collapse-icon"
                  width="20px"
                  height="20px"
                  src="/icons/arrow-left.svg"
                  alt=""
                />
                <span class="text-md text-white font-semibold pl-5"
                  >Collapse Menu</span
                >
              </div>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNav from "./appNav";

export default {
  components: {
    AppNav
  },
  methods: {
    switchNav() {
      document.getElementById("maincnt").classList.remove("noAnimation");
      const nav = document.getElementById("navSlider");
      const mainCont = document.getElementById("maincnt");
      nav.classList.toggle("transform-x-100");
      mainCont.classList.toggle("noMargin");
    },
    minNav() {
      document.getElementById("maincnt").classList.add("noAnimation");
      document.getElementById("navdrawer").classList.toggle("w-drawer-min");
      document.getElementById("maincnt").classList.toggle("main-min-cnt");
      document.getElementById("collapse-menu").classList.toggle("min-nav-w");
      document.getElementById("collapse-icon").classList.toggle("rotate-180");

      const minnavHead = document.getElementsByClassName("nav-head");
      for (let i = 0; i < minnavHead.length; i++) {
        minnavHead[i].classList.toggle("hidden");
      }
      const minnav = document.getElementsByClassName("nav-list");
      for (let i = 0; i < minnav.length; i++) {
        minnav[i].classList.toggle("min-nav");
      }
    }
  }
};
</script>

<style>
.nuxt-link-exact-active div {
  background-color: #edf2f7;
}
</style>
