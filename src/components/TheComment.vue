<template lang="">
    <form @submit="handleComment" >
        <textarea v-bind="$attrs" name="comments" placeholder="Enter your comment" @input="getCommentInputValue" rows="5" cols="35" class="border-2 rounded-lg" id="comments"></textarea>
        <button class="bg-slate-500 px-5 py-2 rounded-lg ml-6" @click="submitComment">{{buttonText}}</button>
    </form>
</template>
<script>
export default {
  props: {
    modelValue: {
      type: String,
      default: "",
    },
    buttonText: {
      type: String,
      default: "Submit",
    },
  },
  setup: ()=>{
    return {
        msg: "Please "
    }
  },
  inheritAttrs: false,
  //   created(){
  //     console.log(this.$attrs);
  //   },
  methods: {
    handleComment(e) {
      e.preventDefault();
      console.log(e.target.comments.value);
    },
  },
  beforeCreate(){
    console.log("beforeCreate");
    console.log(this.msg);
  },
  created() {
    console.log("created");
    console.log(this.msg);
  },
  beforeMount() {
    console.log("beforeMount");
    console.log(this.msg);
  },
  mounted() {
    console.log("mounted");
    console.log(this.msg);
  },
  beforeUpdate() {
    console.log("beforeUpdate");
    console.log(this.msg);
   },
  updated() {
    console.log("updated");
    console.log(this.msg);
   },
   beforeUnmount() {
     console.log("beforeUnmount");
     console.log(this.msg);
    },
    unmounted() {
     console.log("unmounted");
     console.log(this.msg);
    },
  
};
</script>
<style lang="">
</style>