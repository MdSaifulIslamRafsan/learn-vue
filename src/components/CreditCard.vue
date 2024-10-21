<template lang="">
    <div>
        <h1>Credit Card</h1>
        <div class="card">
          <label>
            Name on Card
          </label>
          <input class="border-2" @input="handleCardHolderName" :value="cardHolderName" type="text" />
          <input class="border-2" type="text" :value="cardNumber" @input="handleCardNumber"  />
          <input class="border-2" type="text" :value="expirationDate" @input="handleExpirationDate" />
          <input class="border-2" type="text" :value="cvv" @input="handleCvv" />
        </div>
    </div>
</template>
<script>
export default {
    props: {
        cardHolderName: {
            type: String,
            default : "",
        },
        cardNumber: {
            type: Number,
            default : "",
        },
        expirationDate: {
            type: String,
            default : "",
        },
        cvv: {
            type: String,
            default : "",
        }
    },
    methods: {
        handleCardHolderName(e){
           this.$emit("update:cardHolderName", e.target.value);
        },
        handleCardNumber(e){
           this.$emit("update:cardNumber", e.target.value);
        },
        handleExpirationDate(e){
           this.$emit("update:expirationDate", e.target.value);
        },
        handleCvv(e){
           this.$emit("update:cvv", e.target.value);
        },
    },
   
}
</script>
<style  scoped>


    
   .card {
    width: 300px;
    margin: 0 auto;
    border: 1px solid #ccc;
    padding: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    min-height: 300px;
    }
  
</style>