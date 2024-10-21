<template lang="">
    <div>
        <h1>Credit Card</h1>
        <div class="card">
          
        </div>
    </div>
</template>
<script>
export default {
    setup: () => {
        return {
            cardNumber: '',
            cardHolderName: '',
            expirationDate: '',
            cvv: ''
        }
    }
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