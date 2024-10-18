<template>
  <h1>{{ msg }}</h1>
  <div class="grid grid-cols-3">
    <ContactDetails />
    <ContactDetails />
    <ContactDetails />
  </div>
</template>

<script>
import ContactDetails from "./components/ContactDetails.vue";
export default {
  components: { ContactDetails },
  setup() {
    return {
      msg: "Hello Vue.js!",
    };
  },
  methods: {},
};
</script>
