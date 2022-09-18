<script>
export default {
  data() {
    return {
      category: "Meat",
    };
  },
  emits: ["category"],
  created() {
    this.$emit("category", this.category);
  },
  updated() {
    this.$emit("category", this.category);
  },
};
</script>

<template>
  <div class="weekdayRadioInput">
    <div class="checkbox">
      <input type="radio" value="Meat" v-model="category" />
      <label>Meat</label>
    </div>
    <div class="checkbox">
      <input type="radio" value="Fish" v-model="category" />
      <label>Fish</label>
    </div>
    <div class="checkbox">
      <input type="radio" value="Veggie" v-model="category" />
      <label>Veggie</label>
    </div>
  </div>
</template>

<style>
.weekdayRadioInput {
  display: flex;
  margin-bottom: 20px;
}

.checkbox {
  margin-left: 10px;
  margin-right: 10px;
}
</style>
