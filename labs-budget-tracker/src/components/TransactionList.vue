<template>
  <h1 class="font-bold text-xl pt-5">Mes transactions</h1>
  <div class="pb-6 space-y-3.5">
    <div v-for="transaction in transactions" :key="transaction.id">
      <div class="border-2 border-slate-500 p-4 rounded-xl flex items-center justify-between gap-3 group relative">
        <section class="flex items-center gap-3">
          <div class="bg-slate-200 h-10 w-10 rounded-xl flex items-center justify-center" :class="transaction.amount < 0 ? `bg-red-200` : `bg-blue-200` ">
            <p class="font-extrabold text-lg text-green-600"> {{ transaction.amount < 0 ? "🤬" : "💵"}} </p>
          </div>
          <div>
            <p class="font-bold text-md"> {{ transaction.text }} </p>
            <p class="font-medium text-slate-500 text-xs -mt-0.5"> {{ transaction.amount}} € </p>
          </div>
        </section>
        <button class="rounded-lg px-4 py-0.5 bg-red-200 w-fit hidden group-hover:block group"
                @click="deleteTransaction(transaction.id)"
        >
          <span class="text-sm text-red-700 font-semibold">Supprimer</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>

const emit = defineEmits(['transactionDeleted'])

import { defineProps } from 'vue'
const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  }
})

const deleteTransaction = (id) => {
  emit('transactionDeleted', id)
}

</script>
