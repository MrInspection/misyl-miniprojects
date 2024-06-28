<template>
  <form id="form" class="border-2 rounded-xl p-4 border-slate-500 w-full" @submit.prevent="onSubmit()">

    <div>
      <h1 class="font-bold ">Ajouter une transaction</h1>
      <p class="text-xs text-slate-500">Remplissez le formulaire ci-dessous pour ajouter une transaction</p>
    </div>

    <section class="mt-3 space-y-3">
      <div class="grid space-y-1.5">
        <label for="text" class="text-sm font-medium ">Intitulé de la transaction</label>
        <input v-model="text" type="text" id="text" placeholder="Ex: Achat d'un nouveau ordinateur"
               class="border-2 rounded-lg px-2.5 py-1 text-sm focus:ring-1"
        />
      </div>
      <div class="grid space-y-1.5">
        <label for="amount" class="text-sm">Somme de la transaction</label>
        <input
            type="number" id="amount" placeholder="Somme de la transaction..." v-model="amount"
            class="border-2 rounded-lg px-2.5 py-1 text-sm focus:ring-1"
        />
      </div>
      <button
          class=" bg-blue-200 font-medium rounded-md border-2 border-blue-500 w-full text-sm py-1 text-blue-500
          hover:bg-blue-500 hover:text-white duration-300" type="submit"
      >
      Ajouter une transaction
    </button>
    </section>
  </form>
</template>

<script setup>
import { ref } from 'vue'
import {useToast} from "vue-toastification";

const text = ref('')
const amount = ref('')
const toast = useToast()

const emit = defineEmits(['transactionSubmitted'])

const onSubmit = () => {
  if(!text.value || !amount.value) {
    toast.error("Missing arguments, please fill both fields")
    return
  }

  const transactionData = {
    text: text.value,
    amount: parseFloat(amount.value)
  }

  emit('transactionSubmitted', transactionData)

  text.value = ''
  amount.value = ''

}
</script>
