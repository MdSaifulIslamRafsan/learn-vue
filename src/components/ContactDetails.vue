<template>
   <div class="card">
    <h1>Name: {{contact.name}}</h1>
    <p>Number: {{ contact.phone }} </p>
    <p>Email: {{contact.email}}</p>
   </div>

</template>

<script>
export default {
    // props: ["contact"],
    props: {
      contact: {
        type: Object,
        required: true,
        default: () => ({
          name: '',
          phone: '',
          email: ''
        })
      }
    },

    setup() {
        return {
        }
    },
}
</script>
// when we are scoped use style element it's means this css file only this component work
<style scoped>
    .card{
        border: 1px solid black;
        padding: 20px;
        margin: 10px;
        box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5);
        text-align: center;
        overflow: hidden;
 
    }
</style>