<template lang="">
    <div>
        <div>
            <h1 class="">
                name: {{name}}
            </h1>
            <p>
                age: {{age}}
            </p>
            <p>
                email: {{email}}
            </p>
        </div>
    </div>
</template>
<script>
export default {
    inject: [ "name", "email", "age" ]
}
</script>
<style scoped>

    
</style>