<template>
  <div>
    <appHead />
    <div id="maincnt" class="mainCont transition-small bg-light-gray">
      <nuxt />
    </div>
  </div>
</template>

<script>
import appHead from "~/components/header/appHead.vue";

export default {
  components: {
    appHead
  }
};
</script>

<style>
#navSlider {
  top: 50px;
}
#collapse-menu {
  width: 240px;
}
.bg-light-gray {
  background-color: #f8f8f8;
}
.text-dark-blue {
  color: #040e45;
}
.text-light-blue {
  color: #bec5d2;
}
a {
  text-decoration: none;
  color: #000;
}
.mainCont {
  margin-left: 240px;
  margin-top: 77px;
}
.noMargin {
  margin-left: 0px !important;
}
.w-drawer {
  width: 240px;
}
.transform-x-0 {
  transform: translateX(0%);
}

.transform-x-100 {
  transform: translateX(-100%);
}
.transition-small {
  transition: 0.3s ease-in-out;
}
.z-1 {
  z-index: -1;
}
.min-nav span {
  display: none;
}

.min-nav {
  padding: 20px;
}
.main-min-cnt {
  margin-left: 70px;
}
.w-drawer-min {
  width: 70px;
}
.min-nav-w {
  width: 70px !important;
}
.noAnimation {
  transition: none;
}

.rotate-180 {
  transform: rotate(180deg);
}
</style>
