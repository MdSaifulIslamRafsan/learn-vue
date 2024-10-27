<template>
    <teleport to='#notification'>
                <div class="w-72 m-4 text-center bg-slate-300 py-5 ">
                    {{ message }}
                </div>
    </teleport>
</template>
<script>
export default {
    props: ["message"]
}
</script>
<style scoped>
   
</style>