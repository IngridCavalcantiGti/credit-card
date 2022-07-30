<template>
  <label>
    <span class="label d-block d-flex justify-content-between">
      {{ label }}</span
    >
    <div class="input-group d-flex justify-content-end">
      <input
        class="input"
        type="text"
        :value="value"
        @input="updateInput($event.target.value)"
        :size="size"
      />
      <i class="bi bi-info-circle position-absolute" v-if="icon"></i>
    </div>
  </label>
</template>

<script>
export default {
  name: "Input",
  props: {
    label: {
      type: String,
      required: true,
    },
    icon: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "20",
    },
  },

  setup(props, { emit }) {
    const updateInput = (value) => {
      emit("input", value);
    };

    return {
      updateInput,
    };
  },
};
</script>
<style scoped>
.input {
  padding: 0.3rem;
  border-top: none;
  border-right: none;
  border-left: none;
  background: transparent;
  border-bottom: rgb(39, 16, 122) solid 1px;
}
.label {
  color: gray;
  font-size: 0.8rem;
}

.input:focus-visible {
  border-bottom: rgb(39, 16, 122) solid 1px;
  outline: none;
}
</style>