<script setup>
import { ref, reactive, computed } from "vue";
import { useRouter } from "vue-router";

const customer = ref("");

const product = ref([]);

const valued = reactive({
  ingredient: "",
  amount: 0,
  price: 0,
});

const addProduct = () => {
  product.value.push({ ...valued });
  valued.ingredient = "";
  valued.amount = 0;
  valued.price = 0;
};

const totalAmount = computed(() => {
  return product.value.reduce((total, data) => {
    return total + data.amount;
  }, 0);
});

const totalPrice = computed(() => {
  return product.value.reduce((total, data) => {
    return total + data.amount * data.price;
  }, 0);
});

const deleteProduct = (index) => {
  product.value.splice(index, 1);
};

const router = useRouter();
const payment = () => {
  {
    router.push({
      path: "/payment",
      query: {
        totalAmount: totalAmount.value,
        totalPrice: totalPrice.value,
        customer: customer.value,
      },
    });
  }
};
</script>

<template>
  <div class="container">
    <h1>List Ingredient</h1>
    <div class="customer">
      <label for="customer">
        Customer <br />
        <input type="text" id="customer" name="customer" v-model="customer" />
      </label>
    </div>
    <span>
      <label for="ingredient">
        Ingredient
        <input
          type="text"
          id="ingredient"
          name="ingredient"
          v-model="valued.ingredient" />
      </label>
      <label for="amount">
        Amount
        <input
          type="number"
          id="amount"
          name="amount"
          v-model="valued.amount" />
      </label>
      <label for="price">
        Price
        <input type="number" id="price" name="price" v-model="valued.price" />
      </label>
      <button type="submit" @click="addProduct()">Submit</button>
    </span>
    <table>
      <thead>
        <tr>
          <th>No.</th>
          <th>Ingredient</th>
          <th>Price</th>
          <th>Amount</th>
          <th>Total</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-if="product.length === 0">
          <td colspan="6">Data Empty</td>
        </tr>
        <tr v-for="(data, index) in product" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ data.ingredient }}</td>
          <td>Rp {{ data.price }}</td>
          <td>{{ data.amount }}</td>
          <td>Rp {{ data.amount * data.price }}</td>
          <td>
            <button type="button" @click="deleteProduct(index)">Delete</button>
          </td>
        </tr>
        <tr v-if="product.length > 0">
          <td colspan="3">Total</td>
          <td>{{ totalAmount }}</td>
          <td>Rp {{ totalPrice }}</td>
          <td></td>
        </tr>
      </tbody>
    </table>
    <p>Total Data : {{ product.length }}</p>
    <button type="button" @click="payment()">Cetak Tagihan</button>
  </div>
</template>

<style scoped>
.container {
  text-align: center;
  background-color: black;
  color: white;
}

table,
th,
td {
  border: 1px solid white;
  margin-left: auto;
  margin-right: auto;
}
</style>
