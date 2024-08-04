<script setup>

</script>

<template>
  <q-page class="q-pa-xl">

    <q-input color="teal" filled v-model="text" placeholder="Label" class="custom-input">
      <template v-slot:prepend>
        <q-icon name="mail" />
      </template>
    </q-input>
  </q-page>
</template>

<style scoped>

.custom-input {
  background-color: #f9fafb; /* bg-gray-50 */
  border: 1px solid #d1d5db; /* border border-gray-300 */
  color: #111827; /* text-gray-900 */
  font-size: 0.875rem; /* sm:text-sm */
  border-radius: 0.5rem; /* rounded-lg */
  width: 100%; /* block w-full */
  padding: 0.625rem; /* p-2.5 */
  outline: none; /* Remove default outline */
}

</style>
