<script setup>
import '../Styles/Day5.css'
import { ref, computed } from 'vue'

const Filter = ref(false)
const filter = [
  'Price',
  'Size',
  'Color',
  'Brand'
]
const Product = ref([
  {
    id: 1,
    name: 'IPhone 18',
    available: true
  },
  {
    id: 2,
    name: 'One Plus',
    available: true
  },
  {
    id: 3,
    name: 'Samsung Galaxy',
    available: false
  }
])

const available = true
const Premium = true
const quantity = 5
const availableproduct = computed(() => {
  return Product.value.filter(
    product => product.available
  )
})
</script>

<template>
  <div class="day5-container">

    <div class="day5-product-card">

      <h2>Day 5</h2>

      <h2>IPhone 18</h2>

      <button v-if="available">
        Add to Cart
      </button>

      <p v-if="quantity > 10">
        In Stock
      </p>

      <p v-else-if="quantity >= 5">
        Few Stocks Left
      </p>

      <p v-else>
        Out of Stock
      </p>

      <button @click="Filter = !Filter">
        Filter
      </button>

      <h3>Available Products</h3>

      <TransitionGroup
        name="product"
        tag="ul"
        class="day5-product-list"
      >
        <li
          v-for="product in availableproduct"
          :key="product.id"
          class="day5-product-item"
        >
          {{ product.name }}
        </li>
      </TransitionGroup>

      <Transition name="fade">
        <div v-if="Filter">

          <p
            v-for="item in filter"
            :key="item"
          >
            {{ item }}
          </p>

        </div>
      </Transition>

      <template v-if="Premium">
        <p>Free Delivery</p>
        <p>Discount</p>
      </template>

    </div>

  </div>
</template>