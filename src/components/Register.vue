<template lang="">
    <div>
        <form>
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="name">
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email">
          <label for="password">Password:</label>
          <input type="password" id="password" v-model="password">
          <button @click="submitForm">Submit</button>
        </form>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="">
    
</style>