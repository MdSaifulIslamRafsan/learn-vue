<template>
  <div class="the-card">
    <div class="the-card-title flex justify-between">
      {{ product.name }}
      <p v-if="product.addToFavourite" @click="handleToggleFavourite">star</p>
      <p v-else @click="handleToggleFavourite">unstar</p>
    </div>
    <div class="the-card-body text-center">
      <img class="h-60 mx-auto" :src="product.image" alt="iphone 12 pro max" />
      <p>${{ product.price }}</p>
    </div>
    <div class="the_card_footer">
      <div class="flex justify-center">
        <button
          @click="handleBuyClick"
          class="text-center py-2 mx-4 px-5 bg-blue-500"
          href=""
        >
          buy now
        </button>
        <button
          @click="handleAddClick"
          class="text-center py-2 mx-4 px-5 bg-blue-500"
          href=""
        >
          Add to card
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  mounted() {
    console.log("mounted", this.product);
  },
  props: { product: { type: Object, default: () => ({}) } },
  emits: {
    "buy-now-click": function (data) {
      if (!data) {
        console.error("Invalid data provided for buy-now-click event");
        return false;
      }
     return true;
    },
    "add-to-card-click": function (data) { 
        if (!data) {
        console.error("Invalid data provided for add-to-card-click event");
        return false;
      }
      return true;
    },
    "toggle-favourite": function (data) {
      if (!data) { 
         console.error("Invalid product provided for toggle-favourite event");
        return false; 
        } 
      return true;
    },
  },
  methods: {
    handleBuyClick() {
      this.$emit("buy-now-click", this.product);
    },
    handleAddClick() {
      this.$emit("add-to-card-click", this.product);
    },
    handleToggleFavourite(){
      this.$emit("toggle-favourite", this.product);
    }
  },
};
</script>
<style  scoped>
.the-card {
  border: 1px solid rebeccapurple;
  margin: 10px;
}

.the-card-title {
  background-color: rgb(75, 73, 73);
  padding: 10px;
  color: white;
  font-weight: bold;
}
.the-card-body {
  padding: 10px;
}
.the_card_footer {
  background-color: rgb(75, 73, 73);
  padding: 10px;
  color: white;
  font-weight: bold;
  border-top: 1px solid rebeccapurple;
}
</style>
    