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

          <select multiple class="border" v-model="formData.skills">
             <option selected disabled value="" >skills</option>
             <option value="Python">Python</option>
             <option value="Java">Java</option>
             <option value="JavaScript">JavaScript</option>
             <option value="C++">C++</option>
             <option value="Ruby">Ruby</option>
             <option value="Go">Go</option>
             <option value="Swift">Swift</option>
             <option value="Kotlin">Kotlin</option>
             <option value="Rust">Rust</option>
             <option value="C#">C#</option>
             <option value="SQL">SQL</option>
             <option value="NoSQL">NoSQL</option>
             <option value="AI">AI</option>
             <option value="ML">ML</option>
             <option value="DL">DL</option>
             <option value="NLP">NLP</option>
          </select>

          <br>
          <br>
            <label for="terms">
              <input v-model="formData.agreed" type="checkbox" name="terms" id="terms">
              I agree with the terms and conditions.
            </label>
            <br>
            <label for="">
               <input v-model="formData.socialMedia" type="checkbox" value="facebook"> facebook
            </label>
            <label>
              <input v-model="formData.socialMedia" type="checkbox" value="google"> google
            </label>
            <label>
              <input v-model="formData.socialMedia" value="twitter" type="checkbox"> twitter
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
                gender: '',
                language: '',
                skills: [],
                agreed: false,
                socialMedia: [],
              }
        }
    }
}
</script>
<style scoped>

    
</style>