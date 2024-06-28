<template>
  <div class="border-2 border-slate-500 rounded-xl p-5 w-full">
    <h4 class="text-md font-medium text-slate-500">Votre solde actuel</h4>
    <h1 class="text-xl font-bold">{{ total }} €</h1>
  </div>
</template>

<script setup>
const props = defineProps({
  total: {
    type: Number,
    required: true,
  }
})
</script>
