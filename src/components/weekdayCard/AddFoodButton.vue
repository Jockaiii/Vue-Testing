<script>
export default {
  props: {
    foods: { foodName: "", category: "" },
    category: String,
  },
  data() {
    return {
      input: "",
      newFood: { foodName: String, category: String },
    };
  },
  emits: ["newFood"],
  methods: {
    addFood() {
      if (this.input !== "") {
        this.$emit("newFood");
        this.input = "";
      } else {
        alert("Please enter a food name before you add a food item");
      }
    },
  },
};
</script>

<template>
  <div class="weekdayTextInput">
    <input v-model="input" />
    <button @click="addFood()">Add Food</button>
  </div>
</template>

<style>
.weekdayTextInput {
  margin-bottom: 20px;
}
</style>
