<template>
  <Layout className="space-y-4">
    <p class="text-4xl">Dashboard</p>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
      <StatCard v-for="info in stats" :info="info" :key="info.title" />
    </div>
  </Layout>
</template>

<script>
import Layout from "../components/layout/Layout.vue";
import StatCard from "../components/dashboard/StatCard.vue";

export default {
  data: () => ({
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
  computed: {},
  components: {
    Layout,
    StatCard
  }
};
</script>
