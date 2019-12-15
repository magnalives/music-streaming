<template>
  <div>
    <appHead />
    <div id="maincnt" class="mainCont transition-small">
      <nuxt />
    </div>
  </div>
</template>

<script>
import appHead from "~/components/appHead.vue";

export default {
  components: {
    appHead
  }
};
</script>

<style>
a {
  text-decoration: none;
  color: #000;
}
.mainCont {
  margin-left: 240px;
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
  width: auto;
}

.noAnimation {
  transition: none;
}
</style>