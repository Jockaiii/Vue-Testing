<script>
export default {
  props: {
    validFoodCategories: Array,
    foodItem: Object,
    foods: Array,
  },
  emits: ["foods"],
  methods: {
    removeFood(food) {
      this.$emit(
        "foods",
        this.foods.filter((f) => f.foodName !== food)
      );
    },
  },
};
</script>

<template>
  <button
    v-if="this.validFoodCategories.includes(this.foodItem.category)"
    class="removeButton"
    @click="removeFood(this.foodItem.foodName)"
  >
    Remove
  </button>
</template>

<style scoped>
.removeButton {
  margin-left: 10px;
}
</style>
