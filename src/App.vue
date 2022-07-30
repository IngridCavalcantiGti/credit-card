<template>
  <Input label="Card Number" @input="InputValue" icon size="40" />
  <Button label="NEXT" @onClick="clickNext" />
  <Card
    :numberCard="1234567898751234"
    :validity="1522"
    :name="'INGRID'"
    :cvc="200"
  >
  </Card>
</template>

<script>
import Button from "./components/Button.vue";
import Input from "./components/Input.vue";
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    Button,
    Input,
    Card,
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
