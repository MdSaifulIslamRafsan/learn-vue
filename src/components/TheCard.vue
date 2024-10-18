<template>
    <div class="the-card">
        <div class="the-card-title">
            {{cardTitle}}
        </div>
        <div class="the-card-body">
           <slot>
             <!-- Default content goes here -->
             Card content goes here. This is a slot for custom content. 
             You can use the  element to define where this content will be inserted.
             Replace this text with your desired content.
             
           </slot>
        </div>
    </div>
</template>
<script>
export default {
    props: ["cardTitle"],
    setup() {
        
    }
}
</script>
<style scoped>
    .the-card{
        border: 1px solid rebeccapurple;
        margin: 10px;
    }
  
    .the-card-title{
        background-color: rgb(75, 73, 73);
        padding: 10px;
        color: white;
        font-weight: bold;
    }
    .the-card-body{
        padding: 10px;
    }
</style>