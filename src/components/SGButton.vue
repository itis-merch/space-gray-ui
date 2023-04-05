<script setup></script>

<template>
  <button
    class="
    bg-yellow-300
    hover:bg-yellow-400
    active:bg-yellow-300
    text-stone-900
    py-2
    px-6
    transition
    duration-300
    rounded"
  >
    <slot />
  </button>
</template>

<style scoped>
button {
  font-family: "VkSansDisplay-Bold";
}
</style>
