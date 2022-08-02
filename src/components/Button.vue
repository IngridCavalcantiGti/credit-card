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
  background: #820ad1;
  cursor: pointer;
  border: 1px solid #820ad1;
  border-radius: 2px;
  width: 18rem;
  height: 3rem;
}
.label {
  font-size: 1.5rem;
  display: flex;
  align-content: center;
  justify-content: center;
  font-family: monospace;
  font-weight: 100;
  color: rgb(207, 205, 202);
}
</style>
