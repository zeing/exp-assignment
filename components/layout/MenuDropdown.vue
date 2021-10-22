<template>
  <div @click="clickDrop()" class="flex space-x-2 relative">
    <div class="cursor-pointer">
      <slot></slot>
    </div>
    <div
      class="transition transform ease-in-out duration-300"
      :class="[dropdownIconClass]"
    >
      v
    </div>
    <div
      class="absolute -top-16 rounded transition transform ease-in-out duration-500 right-0 bg-white shadow-md w-full p-2 text-center divide-y divide-black z-10 cursor-pointer"
      :class="[dropdownContentClass]"
    >
      <NuxtLink to="/setting">
        <div class="text-lg font-bold hover:text-gray-600 py-2">
          Setting
        </div>
      </NuxtLink>
      <div class="text-lg font-bold text-red-700 hover:text-red-900 py-2">
        Logout
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    isOpen: false
  }),
  computed: {
    dropdownIconClass() {
      return this.isOpen ? "rotate-180" : "rotate-0";
    },
    dropdownContentClass() {
      return this.isOpen
        ? "translate-y-full  opacity-100"
        : "-translate-y-full opacity-0";
    }
  },
  methods: {
    clickDrop() {
      this.isOpen = !this.isOpen;
      // console.log("clickDrop", this.isOpen);
    }
  }
};
</script>
