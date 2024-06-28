<template>
  <div class="grid grid-cols-2 gap-4">
    <section class="border-2 border-slate-600 rounded-xl p-5">
      <h4 class="text-md font-medium text-slate-500">Vos revenus
      </h4>
      <h1 class="text-xl font-bold text-green-600">{{ income }} €</h1>
    </section>
    <section class="border-2 border-slate-600 rounded-xl p-5">
      <h4 class="text-md font-medium text-slate-500">Vos dépenses</h4>
      <h1 class="text-xl font-bold text-red-600">{{ expenses }} €</h1>
    </section>
  </div>
</template>

<script setup>
  const props = defineProps({
    income: {type: Number, required: true},
    expenses: {type: Number, required: true},
  })
</script>