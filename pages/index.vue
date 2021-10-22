<template>
  <Layout className="space-y-4">
    <p class="text-4xl">Dashboard</p>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
      <StatCard v-for="info in stats" :info="info" :key="info.title" />
    </div>
    <div class="w-full border border-black rounded-md p-8 relative">
      <div
        class="px-8 flex space-x-8 justify-around items-end overflow-x-auto overflow-y-hidden relative z-10"
      >
        <div :class="barClass" class="h-64">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-4">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-48">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-96">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-24">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-36">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-36">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-24">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
        <div :class="barClass" class="h-10">
          <p class="w-full">{{ randomNumber() }}</p>
        </div>
      </div>
      <div class="h-full w-full absolute inset-0 p-8">
        <div class="border-l border-b border-black w-full h-full"></div>
      </div>
    </div>
  </Layout>
</template>

<script>
import Layout from "../components/layout/Layout.vue";
import StatCard from "../components/dashboard/StatCard.vue";

export default {
  data: () => ({
    barClass:
      "relative bg-red-800 hover:bg-red-900 w-16 px-1 md:w-8 rounded-t-md flex justify-center items-center text-white",
    currentIndexSelected: 0,
    stats: [
      {
        title: "User",
        amount: "56,000"
      },
      {
        title: "P/L",
        amount: "12,300"
      },
      {
        title: "Amount",
        amount: "100,300"
      },
      {
        title: "Transactions",
        amount: "4450"
      },
      {
        title: "Score",
        amount: "4.7"
      }
    ]
  }),
  methods: {
    randomNumber() {
      return Math.floor(Math.random() * 100);
    }
  },
  computed: {},
  components: {
    Layout,
    StatCard
  }
};
</script>
