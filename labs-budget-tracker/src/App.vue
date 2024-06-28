<template>
  <main class="flex flex-col items-center justify-center my-20">
    <div class="max-md:px-10 max-w-xl w-full">
      <Header />
      <section class="space-y-3">
        <Balance :total="+total" />
        <IncomeExpenses :income="+income" :expenses="+expenses" />
        <TransactionList :transactions="transactions" @transactionDeleted="handleTransactionDeleted" />
        <AddTransactions @transactionSubmitted="handleTransactionSubmitted" />
      </section>
    </div>
  </main>
</template>

<script setup>
import Header from "@/components/Header.vue";
import Balance from "@/components/Balance.vue";
import IncomeExpenses from "@/components/IncomeExpenses.vue";
import TransactionList from "@/components/TransactionList.vue";
import AddTransactions from "@/components/AddTransactions.vue";

import { ref, computed, onMounted } from 'vue'
import {useToast} from "vue-toastification";

const toast = useToast()

const transactions = ref([])
onMounted(() => {
  const savedTransactions = JSON.parse(localStorage.getItem('transactions'))
  if(savedTransactions) { transactions.value = savedTransactions }

})

const total = computed(() => {
  return transactions.value.reduce((acc, transaction) => {
    return acc + transaction.amount
  }, 0)
})

const income = computed(() => {
  return transactions.value
      .filter((transaction) => transaction.amount > 0)
      .reduce((acc, transaction) => {
    return acc + transaction.amount
  }, 0).toFixed(2)
})

const expenses = computed(() => {
  return transactions.value
      .filter((transaction) => transaction.amount < 0)
      .reduce((acc, transaction) => {
        return acc + transaction.amount
  }, 0).toFixed(2)
})

const handleTransactionSubmitted = (transactionData) => {
  transactions.value.push({
    id: generateUniqueId(),
    text: transactionData.text,
    amount: transactionData.amount,
  })
  saveTransactionsToLocalStorage()
  toast.info("Transaction successfully added")
}

const handleTransactionDeleted = (id) => {
  transactions.value = transactions.value.filter((transaction) => transaction.id !== id)
  saveTransactionsToLocalStorage()
  toast.success("The transaction has been removed")
}

const saveTransactionsToLocalStorage = () => {
  localStorage.setItem('transactions', JSON.stringify(transactions.value))
}

const generateUniqueId = () => {
  return Math.floor(Math.random() * 1000000)
}


</script>
