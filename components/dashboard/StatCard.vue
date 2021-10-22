<template>
  <div
    class="w-full shadow hover:shadow-lg hover:scale-105 transform duration-500 p-4 h-auto border border-black border-opacity-20 rounded-md flex items-end flex-col justify-center select-none"
  >
    <div class="text-lg font-bold">{{ info.title }}</div>
    <div class="text-xl md:text-5xl text-gray-600 font-bold">
      {{ info.amount }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    info: null
  },
  computed: {},
  components: {}
};
</script>
