<script setup>
const {
  data: products,
  pending,
  error,
} = await useFetch("https://fakestoreapi.com/products");

const hasProducts = computed(
  () => products.value.length > 0 && pending.value == false
);
</script>
<template>
  <div>
    <div
      class="grid grid-cols-1 sm:grid-cols-3 lg:grid-cols-4 gap-4"
      v-if="hasProducts"
    >
      <div class="group" v-for="product in products" :key="product.id">
        <NuxtLink :to="`/products/${product.id}`">
          <div class="">
            <div
              class="aspect-h-3 aspect-w-3 w-full overflow-hidden bg-gray-200 lg:aspect-none group-hover:opacity-75 lg:h-80"
            >
              <img
                :src="product.image"
                :alt="product.title"
                class="h-full w-full object-cover object-center lg:h-full lg:w-full group-hover:opacity-75"
              />
            </div>
            <div class="flex justify-between mt-4">
              <h2 class="text-indigo-900 truncate">
                {{ product.title }}
              </h2>
              <p class="font-bold">${{ product.price }}</p>
            </div>
            <div class="mt-4">
              <a
                href="#"
                class="relative flex items-center justify-center rounded-md border border-transparent bg-indigo-800 px-8 py-2 text-sm font-medium text-white hover:bg-indigo-700"
                >Add to cart</a
              >
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>
