<script setup>
const route = useRoute();
const productId = route.params.id;

const { data, pending, error } = await useFetch(
  `https://fakestoreapi.com/products/${productId}`
);
</script>
<template>
  <div>
    <div v-if="data && !pending">
      <div class="lg:grid lg:auto-rows-min lg:grid-cols-12 lg:gap-x-8">
        <div class="lg:col-span-5 lg:col-start-8">
          <div class="flex justify-between">
            <h1 class="text-xl font-medium text-gray-900">{{ data.title }}</h1>
            <p class="text-xl font-medium text-gray-900">${{ data.price }}</p>
          </div>
        </div>

        <!-- Image gallery -->
        <div
          class="mt-8 lg:col-span-7 lg:col-start-1 lg:row-span-3 lg:row-start-1 lg:mt-0"
        >
          <h2 class="sr-only">Images</h2>

          <div class="grid grid-cols-1 lg:grid-cols-2 lg:grid-rows-3 lg:gap-8">
            <img
              :src="data.image"
              alt="Back of women's Basic Tee in black."
              class="lg:col-span-2 lg:row-span-2 rounded-lg"
            />
          </div>
        </div>

        <div class="mt-2 lg:col-span-5">
          <!-- Product details -->
          <div>
            <h2 class="text-sm font-medium text-gray-900">Description</h2>

            <div class="prose prose-sm mt-4 text-gray-500">
              {{ data.description }}
            </div>
          </div>

          <form>
            <button
              type="submit"
              class="mt-4 flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
            >
              Add to cart
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
