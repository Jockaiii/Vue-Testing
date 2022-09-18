<script>
export default {
  data() {
    return {
      validFoodCategories: ["Meat", "Fish", "Veggie"],
    };
  },
  emits: ["validFoodCategories"],
  created() {
    this.$emit("validFoodCategories", this.validFoodCategories);
  },
  updated() {
    this.$emit("validFoodCategories", this.validFoodCategories);
  },
};
</script>

<template>
  <div class="foodCheckerContainer">
    <h3>Select food categories you want displayed:</h3>

    <div class="checkboxes">
      <label>Meat</label>
      <input type="checkbox" value="Meat" v-model="validFoodCategories" />
    </div>

    <div class="checkboxes">
      <label>Fish</label>
      <input type="checkbox" value="Fish" v-model="validFoodCategories" />
    </div>

    <div class="checkboxes">
      <label>Veggie</label>
      <input type="checkbox" value="Veggie" v-model="validFoodCategories" />
    </div>
  </div>
</template>

<style scoped>
.foodCheckerContainer {
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;

  background-color: #fefbe9;
  color: #183a1d;
}

.checkboxes {
  margin-left: 10px;
  margin-right: 10px;
}
</style>
