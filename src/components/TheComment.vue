<template lang="">
    <form @submit="handleComment" >
        <textarea v-bind="$attrs" name="comments" placeholder="Enter your comment" @input="getCommentInputValue" rows="5" cols="35" class="border-2 rounded-lg" id="comments"></textarea>
        <button class="bg-slate-500 px-5 py-2 rounded-lg ml-6" @click="submitComment">{{buttonText}}</button>
    </form>
</template>
<script>
export default {
    props: {  
        modelValue:{
            type: String,
            default: '',
        },
        buttonText:{
            type: String,
            default: 'Submit',
        }
        
      },
      inheritAttrs: false,
      created(){
        console.log(this.$attrs);
      },
    methods: {
        handleComment(e) {
            e.preventDefault();
            console.log(e.target.comments.value);
            
            // getCommentInputValue(e){
            //     console.log(e.target.value)
            // }
        }
    }
}
</script>
<style lang="">
    
</style>