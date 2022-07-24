<template>
  <Button label="NEXT" @onClick="clickNext" />
  <Input label="Card Number" @input="InputValue" icon size="40" />
</template>

<script>
import Button from "./components/Button.vue";
import Input from "./components/Input.vue";

export default {
  name: "App",
  components: {
    Button,
    Input,
  },

  setup() {
    const clickNext = () => {
      alert("click");
    };
    const InputValue = (value) => {
      console.log(value);
    };
    return { clickNext, InputValue };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* body {
  background-color: black !important;
} */
</style>
