<template>
   <div class="card">
    <h1>Name: {{name}}</h1>
    <p>Number: {{ number }} </p>
    <p>website: www.lorem.com</p>
   </div>

</template>

<script>
export default {
    setup() {
        return {
            name: "test",
            number: "123",
        }
    },
}
</script>

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