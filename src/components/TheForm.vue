<template>
    <div class="py-5 px-4">
        <label for="name">
            name
            <br>
            <input class="border-2 border-red-200 px-3 py-2" id="name" name="name" type="text" v-model="formData.FullName"  placeholder="enter your name"/>
        </label>
        <br><br>
        <label for="comment">
            comment
            <br>
            <textarea v-model="formData.comment"  placeholder="comment" id="comment" class="border-2 border-red-200 px-3 py-2"></textarea>
        </label>
        <br>
        <br>
        <!-- {{ formData }} -->
          <div v-for="(value, key) in formData" :key="key">
                <p>{{ key }} : {{ value }}</p>
          </div>
    </div>
</template>
<script>

export default {
    data(){
        return {
            formData:{
                FullName: '',
                comment: '',
            }
        }
    }
}
</script>
<style scoped>

    
</style>