<template>
  <Layout className="space-y-4">
    <div class="text-4xl">Users</div>
    <table class="border-collapse border border-black w-full">
      <thead>
        <tr>
          <th class="border border-black ">Username</th>
          <th class="border border-black ">Name</th>
          <th class="border border-black ">Email</th>
          <th class="border border-black ">Phone Number</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td class="border border-black">{{ user.username }}</td>
          <td class="border border-black">{{ user.name }}</td>
          <td class="border border-black">{{ user.email }}</td>
          <td class="border border-black">{{ user.phone }}</td>
        </tr>
      </tbody>
    </table>
  </Layout>
</template>

<script>
import Footer from "../components/layout/Footer.vue";
import Layout from "../components/layout/Layout.vue";

export default {
  async asyncData({ $axios }) {
    const users =
      (await $axios.$get("https://jsonplaceholder.typicode.com/users")) || [];
    return { users };
  },
  fetchOnServer: false,
  components: {
    Layout,
    Footer
  }
};
</script>
