<template>
  <div class="container">
    <div class="row justify-content-center mt-5">
      <div class="col-6">
        <div class="d-flex justify-content-center">
          <Card
            :cardNumber="cardNumber"
            :expiryDate="expiryDate"
            :name="cardName"
            :cvc="cvc"
          >
          </Card>
        </div>

        <div class="d-flex justify-content-center">
          <Input
            label="Card Number"
            @onInput="InputValue"
            size="50"
            class="mt-5"
            :value="valueCardNumber"
          />
        </div>

        <div class="d-flex justify-content-center mt-5">
          <Input
            label="CVC"
            @onInput="InputCvc"
            size="19"
            icon
            :value="valueCvc"
            title="CVC"
          />
          <Input
            label="Expiry date"
            @onInput="InputExpiryDate"
            size="19"
            icon
            class="ms-5"
            :value="valueExpiryDate"
            title="Expiry date"
          />
        </div>

        <div class="d-flex justify-content-center">
          <Input
            label="Name on Card"
            @onInput="InputCardName"
            size="50"
            class="mt-5"
            :value="valueNameCard"
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
import { ref } from "vue";

export default {
  name: "App",
  components: {
    Button,
    Input,
    Card,
  },

  setup() {
    const cardNumber = ref("");
    const expiryDate = ref("");
    const cvc = ref("");
    const cardName = ref("");

    const valueCardNumber = ref("");
    const valueExpiryDate = ref("");
    const valueCvc = ref("");
    const valueNameCard = ref("");

    const InputValue = (value) => {
      cardNumber.value = value;
    };

    const InputExpiryDate = (value) => {
      expiryDate.value = value;
    };

    const InputCvc = (value) => {
      cvc.value = value;
    };
    const InputCardName = (value) => {
      cardName.value = value.toUpperCase();
    };

    const clickNext = () => {
      cardNumber.value = "";
      cardName.value = "";
      cvc.value = "";
      expiryDate.value = "";
      valueCardNumber.value = null;
      valueNameCard.value = null;
      valueCvc.value = null;
      valueExpiryDate.value = null;
    };
    return {
      clickNext,
      InputValue,
      cardNumber,
      expiryDate,
      InputExpiryDate,
      InputCvc,
      cvc,
      cardName,
      InputCardName,
      valueCardNumber,
      valueNameCard,
      valueCvc,
      valueExpiryDate,
    };
  },
};
</script>

<style>
body {
  background: rgb(48, 48, 48) !important;
}
</style>
