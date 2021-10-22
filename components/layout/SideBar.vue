<template>
  <div
    style="width: 300px"
    class="px-8 py-4 space-y-6 flex-col bg-green-100 h-screen shadow z-10 transition duration-500 flex fixed left-0 transform"
    :class="openClass"
  >
    <NuxtLink
      v-for="menu in menues"
      :to="menu.url"
      :key="menu.name"
      class="text-lg font-bold hover:text-gray-600"
    >
      {{ menu.name }}
    </NuxtLink>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: Boolean
  },
  data: () => ({
    menues: [
      { name: "Home", url: "/" },
      { name: "Users", url: "/users" },
      { name: "Setting", url: "/setting" }
    ]
  }),
  computed: {
    openClass() {
      console.log("this.isOpen", this.isOpen);
      return this.isOpen ? "translate-x-0" : "-translate-x-full	";
    }
  }
};
</script>
