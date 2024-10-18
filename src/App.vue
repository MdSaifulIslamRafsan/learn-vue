<template>
  <h1>{{ msg }}</h1>
  <ContactDetails></ContactDetails> 
</template>

<script>
import ContactDetails from './components/ContactDetails.vue'
export default {
  components: { ContactDetails },
  setup() {
    return {
      msg: 'Hello Vue.js!',
    }
  },
  methods: {},
}
</script>
