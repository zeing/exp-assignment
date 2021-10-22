<template>
  <div class="flex w-full bg-gray-100 shadow-md">
    <div
      class="flex justify-between text-black container mx-auto text-lg items-center py-4 px-4 md:px-0"
    >
      <div class="flex space-x-4 items-center">
        <div class="cursor-pointer" @click="$emit('update:isOpen', !isOpen)">
          =
        </div>
        <div>EXP</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: Boolean
  }
};
</script>
