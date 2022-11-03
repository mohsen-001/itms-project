<template>
  <div class="check-container">
    <input :id="for_name" type="checkbox" :name="for_name" />
    <label :for="for_name">{{ checkbox_label }}</label>
  </div>
</template>

<script>
export default {
  name: "Check-box",
  props: ["checkbox_label", "for_name"],
};
</script>

<style scoped>
.check-container {
  display: flex;
  align-items: center;
}

input[type="checkbox"] {
  appearance: none;
  width: 18px;
  height: 18px;
  background-color: transparent;
  border: 2px solid #c2c2c2;
  border-radius: 5px;
  position: relative;
  margin-right: 8px;
}

input[type="checkbox"]::after {
  content: "";
  position: absolute;
  width: 10px;
  height: 10px;
  background-color: var(--primary-color);
  border-radius: 2.5px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: none;
}

input[type="checkbox"]:checked::after {
  display: block;
}
</style>
