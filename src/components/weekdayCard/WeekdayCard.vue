<script>
import FoodItem from "./FoodItem.vue";
import RemoveFoodButton from "./RemoveFoodButton.vue";
import FoodInput from "./FoodInput.vue";
import AddFoodButton from "./AddFoodButton.vue";

export default {
  components: {
    FoodItem,
    RemoveFoodButton,
    FoodInput,
    AddFoodButton,
  },
  props: {
    validFoodCategories: Array,
    weekday: String,
  },
  data() {
    return {
      foods: [{ foodName: "", category: "" }],
      category: "",
    };
  },
};
</script>

<template>
  <div class="weekdayCard">
    <h3>{{ weekday }}</h3>

    <div class="weekdayListContainer">
      <ul class="weekdayList">
        <div
          class="weekdayListItem"
          v-for="(newFood, index) in foods"
          :key="index"
        >
          <FoodItem
            :foodItem="newFood"
            :validFoodCategories="validFoodCategories"
          ></FoodItem>

          <RemoveFoodButton
            :foods="foods"
            :foodItem="newFood"
            :validFoodCategories="validFoodCategories"
            @foods="(foods) => (this.foods = foods)"
          ></RemoveFoodButton>
        </div>
      </ul>

      <FoodInput
        @category="(category) => (this.category = category)"
      ></FoodInput>

      <AddFoodButton
        :foods="foods"
        :category="this.category"
        @newFood="(newFood) => this.foods.push(newFood)"
      ></AddFoodButton>
    </div>
  </div>
</template>

<style scoped>
.weekdayCard {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  align-items: center;

  border: 1px solid black;
  border-radius: 20px;

  margin-top: 20px;
  margin-left: 10px;
  margin-right: 10px;

  width: 300px;

  background-color: #e1eedd;
}

.weekdayListContainer {
  display: flex;
  flex-direction: column;
  align-items: center;

  width: 100%;
}
.weekdayList {
  display: flex;
  flex-direction: column;
}

.weekdayListItem {
  display: flex;
  margin-top: 10px;
}
</style>
