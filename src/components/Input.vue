<script>

export default {
  name: "input-com",
  data() {
    return {};
  },
  props: {
    input_placeHolder: undefined,
    label_text: undefined,
    input_type: undefined,
    for_name: undefined,
    value: undefined,
    form_control: undefined,
    msg_text: {
      type: undefined,
      default: "This field cannot be empty!",
    },
  },
  methods: {
    updateValue(value) {
      this.$emit("input", value);
    },
    // checkEmail() {
    //   console.log("hey");
    // },
  },
};
</script>

<template>
  <div :class="form_control">
    <label :for="for_name">{{ label_text }}</label>
    <input
      :type="input_type"
      :name="for_name"
      :id="for_name"
      :placeholder="input_placeHolder"
      :value="value"
      @input="updateValue($event.target.value)"
    />
    <small>{{ msg_text }}</small>
    <i class="fa-solid fa-circle-exclamation"></i>
    <i class="fa-solid fa-circle-check"></i>
  </div>
</template>
<!-- style here -->
<style scoped>
.g-form-control {
  position: relative;
}

.g-form-control input {
  width: 287px;
  height: 53px;
  display: block;
  border-radius: 5px;
  border: none;
  background-color: var(--input-color);
  padding: 16px;
  font-size: 16px;
}

.g-form-control input:focus {
  outline: none;
  border: 2px solid var(--primary-color);
  box-shadow: 0 0 10px 0 rgba(71, 181, 255, 0.3);
  background-color: white;
}

.g-form-control input::placeholder {
  font-size: 14px;
  color: #868686;
  opacity: 0.5;
  font-weight: 500;
}

.g-form-control label {
  display: block;
  font-size: 16px;
  color: var(--black-color);
  margin-bottom: 5px;
  font-weight: 500;
}
.g-form-control {
  margin-bottom: 5px !important;
}

.g-form-control small {
  color: red;
  visibility: hidden;
}

.g-form-control.g-error input {
  border: 2px solid red;
}

.g-form-control.g-success input {
  border: 2px solid rgb(1, 171, 1);
}

.g-form-control i {
  position: absolute;
  right: 10px;
  top: 48px;
  visibility: hidden;
}

.g-form-control.g-success i.fa-circle-check {
  color: rgb(1, 171, 1);
  visibility: visible;
}

.g-form-control.g-error i.fa-circle-exclamation {
  color: red;
  visibility: visible;
}

.g-form-control.g-error small {
  color: red;
  visibility: visible;
}
</style>
