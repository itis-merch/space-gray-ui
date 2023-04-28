<script setup>
</script>

<template>
  <div class="flex flex-row">
    <div class="mt-3 w-16">
      <img src="../assets/barcode.png" alt="your-image" class="inline-flex">
    </div>
    <nav class="w-64 flex-shrink-0 h-screen">
      <ul class="flex flex-col">
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900">
          <router-link :to="{ path: '/'}">New Arrivals</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900">
          <router-link href="#">Categories</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900 ml-5">
          <router-link href="#">All products</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900 ml-5">
          <router-link href="#">Hoodies</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900 ml-5">
          <router-link href="#">T-Shirts</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900 ml-5">
          <router-link href="#">Sweatshirts</router-link>
        </li>
        <li class="px-3 py-2 text-stone-800 hover:text-stone-900 ml-5">
          <router-link href="#">Stickers</router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<style scoped>
.flex {
  display: flex;
  align-items: stretch;
}
</style>

<script>
export default {
  name: 'SideBar',
  components: {},
}
</script>
