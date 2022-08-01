<template>
  <div class="card text-white">
    <div class="d-flex justify-content-between">
      <span class="ms-4 mt-3">
        <img alt="chip" src="@/assets/chip.png" class="chip" />
      </span>
      <span class="mt-3 me-4">{{ brand }} brand</span>
    </div>
    <div class="">
      <span class="d-flex justify-content-center mt-4"> {{ numberCard }}</span>
      <div class="mt-4">
        <div class="d-flex justify-content-between">
          <span class="cvc ms-4"> cvc </span>
          <span class="valid me-4"> Expiry Date </span>
        </div>
        <div class="d-flex justify-content-between">
          <span class="ms-4">{{ cvc }}</span>
          <span class="me-4">{{ expiryDate }}</span>
        </div>
      </div>
    </div>
    <div class="d-flex justify-content-center">
      {{ name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    numberCard: { type: Number },
    expiryDate: { type: Number },
    brand: { type: Image },
    name: { type: String },
    cvc: { type: Number },
  },
};
</script>


<style scoped>
.card {
  width: 22rem;
  height: 12rem;
  border: none;
  border-radius: 10px;
  background-color: rgb(88, 122, 235);
}
.cvc,
.valid {
  font-size: 0.7rem;
}
.chip {
  width: 2.4rem;
  height: 2rem;
}
</style>