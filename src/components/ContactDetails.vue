<template>
    <h1>Name: {{name}}</h1>
    <p> Number: {{ number }} </p>

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