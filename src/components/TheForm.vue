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
        <label for="">Gender</label> <br>
          <label for="male">
              <input v-model="formData.gender" type="radio" name="gender" id="male" value="Male">
            Male
          </label>
          <br>
          <label for="Female">
              <input v-model="formData.gender" type="radio" name="gender" id="Female" value="Female">
            Female
          </label>
          <br>
          <label for="Other">
              <input value="Other"  v-model="formData.gender" type="radio" name="gender" id="Other" >
            Other
          </label>
          <br>
          <br>
            <select class="border-2" v-model="formData.language">
             <option selected disabled value="">language</option>
             <option value="Bangla">Bangla</option>
             <option value="English">English</option>

            </select>
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
                gender: '',
                language: '',
              }
        }
    }
}
</script>
<style scoped>

    
</style>