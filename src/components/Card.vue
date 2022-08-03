<template>
  <div class="card">
    <div class="card-container">
      <div class="card-front">
        <div class="d-flex justify-content-between">
          <span class="ms-4 mt-3">
            <img alt="chip" src="@/assets/chip.png" class="chip" />
          </span>
          <span class="mt-3 me-4">
            <img alt="chip" src="@/assets/Mastercard.png" class="chip" />
          </span>
        </div>
        <div class="">
          <span class="d-flex justify-content-center mt-4">
            {{ cardNumber }}</span
          >
          <div class="mt-4 h-35">
            <div class="d-flex justify-content-end">
              <span class="valid me-4"> Expiry Date </span>
            </div>
            <div class="d-flex justify-content-end">
              <span class="me-4">{{ expiryDate }}</span>
            </div>
          </div>
        </div>
        <div class="d-flex justify-content-center">
          {{ name }}
        </div>
      </div>
      <div class="card-back">
        <div class="line mt-4"></div>
        <span class="cvc ms-4 mt-3 d-block"> cvc </span>
        <span class="ms-4">{{ cvc }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cardNumber: { type: String },
    expiryDate: { type: String },
    name: { type: String },
    cvc: { type: String },
  },
};
</script>


<style scoped>
.card {
  width: 21rem;
  height: 12rem;
  border: none;
  border-radius: 10px;
  background-color: transparent;
  perspective: 1000px;
  color: rgb(207, 205, 202);
}
.card-container {
  position: relative;
  height: 100%;
  transition: transform 0.5s;
  transform-style: preserve-3d;
}
.card:hover .card-container {
  transform: rotateY(180deg);
}
.card-front,
.card-back {
  position: absolute;
  width: 100%;
  backface-visibility: hidden;
  z-index: 1;
}

.card-front {
  border: none;
  border-radius: 10px;
  background-color: #820ad1;
  width: 21rem;
  height: 12rem;
}
.card-back {
  transform: rotateY(180deg);
  background: #820ad1;
  width: 21rem;
  height: 12rem;
  border: none;
  border-radius: 10px;
}
.cvc,
.valid {
  font-size: 0.7rem;
  color: rgb(168, 164, 164);
}
.chip {
  width: 2.4rem;
  height: 2rem;
}

.line {
  width: 21rem;
  height: 2.2rem;
  background: rgb(143, 135, 135);
}
.h-35 {
  height: 3.5rem;
}
</style>