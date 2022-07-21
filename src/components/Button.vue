<template>
  <button class="button" @click="() => $emit('onClick')">
    <span class="label">{{ label }}</span>
  </button>
</template>

<script>
export default {
  props: {
    label: { type: String },
  },
};
</script>

<style scoped>
.button {
  background: #07b6ad;
  cursor: pointer;
  border: 1px solid #07b6ad;
  border-radius: 2px;
  width: 28rem;
  height: 4rem;
}
.label {
  font-size: 2rem;
  display: flex;
  align-content: center;
  justify-content: center;
  font-family: monospace;
  font-weight: 100;
  color: rgb(235, 229, 229);
}
</style>
