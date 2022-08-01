<template>
  <div class="container">
    <div class="row justify-content-center mt-5">
      <div class="col-6">
        <div class="d-flex justify-content-center">
          <Card
            :numberCard="1234567898751234"
            :expiryDate="1522"
            :name="'INGRID'"
            :cvc="200"
          >
          </Card>
        </div>

        <div class="d-flex justify-content-center">
          <Input
            label="Card Number"
            @input="InputValue"
            size="50"
            class="mt-5"
          />
        </div>

        <div class="d-flex justify-content-center mt-5">
          <Input label="CVC" @input="InputValue" size="20" icon />
          <Input
            label="Expiry date"
            @input="InputValue"
            size="20"
            icon
            class="ms-5"
          />
        </div>

        <div class="d-flex justify-content-center">
          <Input
            label="Name on Card"
            @input="InputValue"
            size="50"
            class="mt-5"
          />
        </div>
        <div class="d-flex justify-content-center">
          <Button label="NEXT" @onClick="clickNext" class="mt-5" />
        </div>
      </div>
    </div>
  </div>
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
