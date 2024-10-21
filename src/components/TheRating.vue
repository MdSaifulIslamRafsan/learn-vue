<template lang="">
    <div>
        {{message}}
        <div @click="handleClick(index)" class="flex" v-for="index in 5" :key="index">
            <p class="inline text-5xl" v-if="modelValue >= index">*</p>
            <p class="inline text-5xl" v-if="modelValue < index">#</p>
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
    methods:{
        handleClick(index){
            this.$emit('update:modelValue', index);
        }
     },
    setup: ()=>{
        return {
            message : "Welcome",
        }
    }
}
</script>
<style scoped>

</style>