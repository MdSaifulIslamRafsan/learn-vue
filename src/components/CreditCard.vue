<template lang="">
    <div>
        <h1>Credit Card</h1>
        <div class="card">
          <label>
            Name on Card
          </label>
          <input class="border-2" @input="handleCardHolderName" :value="cardHolderName" type="text" />
          <br> <br>
          <label>
            Card Number
          </label>
          <input class="border-2" type="text" :value="cardNumber" @input="handleCardNumber" maxlength="16" />
          <br> <br>
         <div class="grid grid-cols-2 items-center gap-4">
           <div>
            <label>
            Expiration Date (MM/YY)
          </label>
          <input class="border-2" type="text" :value="expirationDate" @input="handleExpirationDate" maxlength="5" />
           </div>
           <div>
            <label>
                CVV
            </label>
            <br>
          
          <input class="border-2" type="text" :value="cvv" @input="handleCvv" maxlength="3" />
           </div>
         </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    cardHolderName: {
      type: String,
      default: "",
    },
    cardNumber: {
      type: String,
      default: "",
    },
    expirationDate: {
      type: String,
      default: "",
    },
    cvv: {
      type: String,
      default: "",
    },
  },
  methods: {
    handleCardHolderName(e) {
      this.$emit("update:cardHolderName", e.target.value);
    },
    handleCardNumber(e) {
      this.$emit("update:cardNumber", e.target.value.replace(/\D/g, "")); // Only digits
    },
    handleExpirationDate(e) {
      let value = e.target.value.replace(/\D/g, ""); // Only digits

      if (value.length >= 2) {
        value = value.slice(0, 2) + "/" + value.slice(2, 4);
      }

      this.$emit("update:expirationDate", value);
    },
    handleCvv(e) {
      this.$emit("update:cvv", e.target.value.replace(/\D/g, "").slice(0, 3)); // Limit to 3 digits
    },
  },
};
</script>

<style scoped>
.card {
  width: 500px;
  margin: 0 auto;
  border: 1px solid #ccc;
  padding: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  min-height: 300px;
}
</style>
