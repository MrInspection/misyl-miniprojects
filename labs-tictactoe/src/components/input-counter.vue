<script setup>
import { ref, watch } from 'vue';

const props = defineProps({
  message: {
    type: String,
    required: true,
  }
});

const hello = ref(props.message);
watch(() => props.message, (newMessage) => {
  hello.value = newMessage;
});
</script>

<template>
  <section class="">
    <div class="grid space-y-1">
      <input type="text" v-model="hello" class="rounded-lg bg-slate-50 px-3 py-1 text-xs border-2 border-slate-500 w-80 focus:border-2">
      <span class="text-sm text-slate-500">
         Characters : {{ hello.length === 0 ? "Nothing" : hello.length + " chars"}}
      </span>
    </div>
  </section>
</template>

