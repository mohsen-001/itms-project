<template>
  <button @click.prevent="$emit('check')" class="g-btn g-btn-primary">{{ btn_text }}</button>
</template>

<script>
export default {
  name: "button-com",
  props: ["btn_text"],
  emits: ['check'],
  methods: {},
};
</script>

<style scoped>
.g-btn {
  padding: 14px 24px;
  border-radius: 10px;
  border: none;
  text-transform: uppercase;
  font-size: 16px;
  font-weight: 700;
  letter-spacing: 1px;
  cursor: pointer;
  transition: 0.1s linear;
}

.g-btn-primary {
  background-color: var(--primary-color);
  color: white;
}

.g-btn-primary:hover {
  background: var(--primary-color-hover);
}

.g-btn-secondary {
  background-color: transparent;
  border: 1px solid rgba(71, 181, 255, 0.5);
  color: var(--primary-color);
}

.g-btn-secondary:hover {
  background: var(--secondary-color-hover);
}

.g-btn-tertiary {
  background-color: transparent;
  color: var(--primary-color);
}

.g-btn-tertiary:hover {
  background: var(--secondary-color-hover);
}
</style>
