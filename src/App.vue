<template>
  <h1>{{ msg }}</h1>
  <div class="grid grid-cols-3">
    <ContactDetails :contact="contact1" />
    <ContactDetails :contact="contact2" />
    <ContactDetails :contact="contact3" />
  </div>
</template>

<script>
import ContactDetails from "./components/ContactDetails.vue";
export default {
  components: { ContactDetails },
  setup() {
    return {
      msg: "Hello Vue.js!",
      contact1: {
        name: "John Doe",
        phone: "123-456-7890",
        email: "john.doe@example.com",
      },
      contact2: {
        name: "Jane Smith",
        phone: "987-654-3210",
        email: "janesmith@example.com",
      },
      contact3: {
        name: "Alice Johnson",
        phone: "555-555-5555",
        email: "alicejohnson@example.com",
      },
    };
  },
  methods: {},
};
</script>
