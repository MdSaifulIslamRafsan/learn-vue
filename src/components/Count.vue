<template lang="">
    <div>
        <h2>{{count}}</h2>
        
        <button class="py-3 px-7 bg-slate-300" @click="count++">increment</button>

    </div>
</template>
<script>
import { ref } from 'vue'


export default {
    
    setup: () => {
        const count = ref(0)
        return {
             count,
        }
    }
}
</script>
<style lang="">
    
</style>