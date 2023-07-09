<template>
  <div class="max-w-7xl mx-auto px-4 lg:px-6">
    <NuxtLoadingIndicator />
    <div
      class="h-16 flex items-center justify-between bg-indigo-100 px-4 rounded my-4"
    >
      <NuxtLink to="/">
        <div class="flex gap-x-4">
          <Icon
            class="w-8 h-8 text-indigo-800 group-hover:text-indigo-600"
            name="grommet-icons:basket"
          />
          <h1
            class="font-bold text-3xl text-indigo-800 italic group-hover:opacity-75"
          >
            FakeStore
          </h1>
        </div>
      </NuxtLink>
      <ul class="flex gap-x-4">
        <li>
          <NuxtLink to="/products" class="text-indigo-800"> Products </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/products" class="text-indigo-800"> About </NuxtLink>
        </li>
      </ul>
      <ul class="flex gap-x-4">
        <li>
          <NuxtLink to="/login" class="text-indigo-800"> Login </NuxtLink>
        </li>
        <li>
          <NuxtLink to="/login" class="text-indigo-800"> Register </NuxtLink>
        </li>
      </ul>
    </div>

    <NuxtLoadingIndicator />
    <!-- here -->
    <NuxtPage />
  </div>
</template>
