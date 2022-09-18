<script>
export default {
  props: {
    validFoodCategories: Array,
    foodItem: Object,
  },
};
</script>

<template>
  <div
    class="foodItem"
    v-if="this.validFoodCategories.includes(this.foodItem.category)"
  >
    <li>{{ this.foodItem.foodName }} {{ this.foodItem.category }}</li>
  </div>
</template>

<style scoped>
.foodItem {
  max-width: 170px;
}
</style>
