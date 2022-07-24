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
      <!-- <the-mask
        mask="#XSAa"
        value="12TgB"
        type="text"
        masked="true"
        placeholder="test your mask here"
      ></the-mask> -->
      <i class="bi bi-info-circle position-absolute" v-if="icon"></i>
    </div>
  </label>
</template>

<script>
// import { TheMask } from "vue-the-mask";
// import { computed } from "vue";
export default {
  // components: { TheMask },
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

    // const sizeInput = computed(() => (props.sizeLg ? "40" : "null"));

    return {
      updateInput,
      // sizeInput,
    };
  },
  //   computed: {
  //     name() {
  //       return this.label.toLowerCase();
  //     },
  //     model: {
  //       get() {
  //         return this.value;
  //       },
  //       set(value) {
  //         this.$emit('input', value);
  //       },
  //     },
  //   },
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
}

.input:focus-visible {
  border-bottom: rgb(39, 16, 122) solid 1px;
  outline: none;
}
.sizeLg {
  background: red;
}
</style>