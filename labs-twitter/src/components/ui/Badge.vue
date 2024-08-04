<script setup>
defineProps({
  label: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="badge">
    <p class="badge-text">
      {{ label }}
    </p>
  </div>

</template>

<style scoped>
.badge {
  border-radius: 0.75rem; /* rounded-xl */
  background-color: #f0f9ff; /* bg-sky-50 */
  padding-left: 0.625rem; /* px-2.5 */
  padding-right: 0.625rem; /* px-2.5 */
  padding-top: 0.375rem; /* py-1.5 */
  padding-bottom: 0.375rem; /* py-1.5 */
  width: fit-content; /* w-fit */
  display: inline-block; /* Ensures the div fits the content */
}

.badge-text {
  font-weight: 600; /* font-semibold */
  color: #0284c7; /* text-sky-600 */
  font-size: 0.75rem; /* text-xs */
  margin: 0; /* Remove default margin */
  line-height: 1; /* Ensure single line-height */
}

</style>
