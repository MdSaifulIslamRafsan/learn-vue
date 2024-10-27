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
</div>
<!-- <Login v-if="activeTab === 'Login'"></Login>
<Register v-if="activeTab === 'Register'"></Register> -->
<keep-alive>
  <component :is="activeTab"></component>
</keep-alive>
</template>
<script>
import { ref } from "vue";
import Login from "./Login.vue";
import Register from "./Register.vue";
import Contact from "./Contact.vue";

export default {
  components: { Login, Register, Contact },
  setup: () => {
    return {
      tabs: ["Login", "Register", "Contact"],
      activeTab: ref("Login"),
      name: ref("md saiful islam"),
      age: ref(22),
      email: ref("md@example.com")
    };
  },
  provide(){
    return {
      name: this.name,
      age: this.age,
      email: this.email
    }
  }
};
</script>
<style>
</style>