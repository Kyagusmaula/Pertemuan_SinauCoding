<script setup>
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const goBack = useRouter();
const customer = route.query.customer;
const totalAmount = route.query.totalAmount;
const totalPrice = route.query.totalPrice;
</script>

<template>
  <div class="payment-container">
    <div class="payment-box">
      <h1>Payment</h1>
      <p>
        Total pembayaran yang harus dibayarkan oleh {{ customer }} dari
        {{ totalAmount }} item sebesar <br />
        Rp {{ totalPrice }},00
      </p>
      <button type="button" @click="goBack.back()">Back</button>
    </div>
  </div>
</template>

<style scoped>
.payment-container {
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.payment-box {
  text-align: center;
  border: 1px solid;
}

.payment-box p {
  font-size: 20px;
}

.payment-box button {
  border: 1px solid;
  font-size: 20px;
  padding: 15px 25px;
  cursor: pointer;
  background-color: black;
  color: white;
}

button:hover {
  background-color: grey;
}
</style>
