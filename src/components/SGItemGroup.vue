<template>
  <div class="py-2">
    <p class="px-3 text-gray-600">{{ title }}</p>
    <ul class="mt-2">
      <slot></slot>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MenuItemGroup',
  props: {
    title: {
      type: String,
      required: true
    }
  }
};
</script>
