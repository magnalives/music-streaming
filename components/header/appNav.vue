<template>
  <div>
    <div class="pl-10 py-3 flex items-center nav-list nav-head-wrapper">
      <div class="text-md font-semibold text-light-blue nav-head">
        Browse Music
      </div>
    </div>
    <div v-for="(navItem, index) in navItems" :key="index">
      <nuxt-link :to="navItem.url">
        <div class="pl-10 py-3 flex items-center nav-list">
          <img :src="navItem.icon" />
          <span class="text-md font-semibold pl-5 text-dark-blue">{{
            navItem.name
          }}</span>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navItems: [
        {
          name: "Discover",
          icon: "/icons/explore.svg",
          url: "/"
        },
        {
          name: "Collections",
          icon: "/icons/collections.svg",
          url: "/collections"
        },
        {
          name: "Artists",
          icon: "/icons/artists.svg",
          url: "/artists"
        },
        {
          name: "Albums",
          icon: "/icons/albums.svg",
          url: "/albums"
        },
        {
          name: "History",
          icon: "/icons/history.svg",
          url: "/history"
        },
        {
          name: "Favourtires",
          icon: "/icons/favourtires.svg",
          url: "/favourtires"
        }
      ]
    };
  }
};
</script>

<style></style>
