<template>
  <div class="flex gap-5 my-7">
    <button
      @click="activeTab = tab"
      class="py-2 px-5 bg-gray-200 rounded-sm"
      v-for="tab in tabs"
      :key="tab"
      :class="{ '!bg-green-500': activeTab === tab }"
    >
      {{ tab }}
    </button>
    <!-- <Login v-if="activeTab === 'Login'"></Login>
  <Register v-if="activeTab === 'Register'"></Register> -->
    <keep-alive>
      <component :is="activeTab"></component>
    </keep-alive>
  </div>
</template>
<script>
import { ref } from "vue";
import Login from "./Login.vue";
import Register from "./Register.vue";

export default {
  components: { Login, Register },
  setup: () => {
    return {
      tabs: ["Login", "Register"],
      activeTab: ref("Login"),
    };
  },
};
</script>
<style>
</style>