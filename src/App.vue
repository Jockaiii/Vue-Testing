<script>
import validFoodCategories from "./components/ValidFoodCategories.vue";
import WeekdayCard from "./components/weekdayCard/WeekdayCard.vue";

export default {
  components: {
    validFoodCategories,
    WeekdayCard,
  },
  data() {
    return {
      validFoodCategories: [],
      weekdays: [
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
        "Sunday",
      ],
    };
  },
};
</script>

<template>
  <div class="content">
    <validFoodCategories
      class="validFoodCategories"
      @validFoodCategories="
        (validFoodCategories) =>
          (this.validFoodCategories = validFoodCategories)
      "
    />
    <WeekdayCard
      v-for="(day, index) in weekdays"
      :validFoodCategories="validFoodCategories"
      :weekday="day"
      :key="index"
    />
  </div>
</template>

<style scoped>
.content {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;

  background-color: #fefbe9;
  color: #183a1d;
  font-family: "Courier New", Courier, monospace;
}

.validFoodCategories {
  display: flex;
  width: 100%;
}
</style>
