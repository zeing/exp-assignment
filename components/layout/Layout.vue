<template>
  <div class="flex flex-col h-screen">
    <Header :isOpen.sync="openDrawer" />
    <div class="flex h-screen overflow-hidden relative">
      <div
        class="bg-black bg-opacity-10 h-screen w-full absolute top-0 z-10"
        :class="[openDrawer ? '' : 'hidden']"
        @click="openDrawer = !openDrawer"
      />
      <SideBar :isOpen="openDrawer" />

      <div
        class="flex-1 px-4 md:px-0 py-4 overflow-y-auto container mx-auto"
        :class="className"
      >
        <slot></slot>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from "./Footer.vue";
import Header from "./Header.vue";
import SideBar from "./SideBar.vue";

export default {
  props: {
    className: ""
  },
  data: () => ({
    openDrawer: false
  }),

  computed: {},
  components: {
    Footer,
    Header,
    SideBar
  }
};
</script>
