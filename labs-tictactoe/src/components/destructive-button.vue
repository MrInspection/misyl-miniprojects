<script setup>

defineProps({
  label: {
    type: String,
    required: true,
  }
})

</script>

<template>
  <button
      class="text-sm bg-red-50 border-2 border-red-500 rounded-md text-red-500 py-0.5
      px-3 font-medium hover:text-white hover:bg-red-500"
  >
    {{ label }}
  </button>
</template>
