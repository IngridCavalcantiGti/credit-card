<template>
  <label>
    <span class="label d-block d-flex justify-content-between">
      {{ label }}</span
    >
    <div class="input-group d-flex justify-content-end">
      <input
        class="input"
        type="text"
        @input="updateInput($event.target.value)"
        :size="size"
        :value="value"
      />
      <i
        class="bi bi-info-circle position-absolute"
        v-if="icon"
        :title="title"
      ></i>
    </div>
  </label>
</template>

<script>
export default {
  name: "Input",
  props: {
    label: {
      type: String,
    },
    icon: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "20",
    },
    value: {
      type: String,
    },
    title: {
      type: String,
    },
  },

  setup(props, { emit }) {
    const updateInput = (value) => {
      emit("onInput", value);
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
  border-bottom: rgb(106, 80, 199) solid 2px;
  color: white;
}
.label {
  color: rgb(168, 164, 164);
  font-size: 0.8rem;
}

.input:focus-visible {
  border-bottom: rgb(106, 80, 199) solid 2px;
  outline: none;
}
.bi-info-circle {
  color: rgb(118, 118, 118);
}
</style>