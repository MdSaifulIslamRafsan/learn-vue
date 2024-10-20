<template lang="">
    <div>
        {{message}}
        <div class="flex" v-for="index in 5" :key="index">
            <p class="inline" v-if="modelValue >= index">*</p>
        </div>


    </div>
</template>
<script>
export default {
    props:{
        modelValue : {
            type: Number,
            required: true,
            default: 0
        }
    },
    emits:[
        'update:modelValue'
    ],
    setup: ()=>{
        return {
            message : "Welcome",
        }
    }
}
</script>
<style scoped>

</style>