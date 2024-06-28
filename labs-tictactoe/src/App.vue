<script setup>
import {ref, computed} from "vue";
import Button from "@/components/Button.vue";
import DestructiveButton from "@/components/destructive-button.vue";
const player = ref("x")
const board = ref([
    ['','',''],
    ['','',''],
    ['','',''],
])

const calculateWinner = (squares) => {
  const lines = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ]
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}

const winner = computed(() => calculateWinner(board.value.flat()))
const MakeMove = (x, y) => {
  if(winner.value) return;
  if (board.value[x][y] !== '') return;
  board.value[x][y] = player.value
  player.value = player.value === 'X' ? 'O' : 'X'
}

const ResetGame = () => {
  board.value = [
    ['','',''],
    ['','',''],
    ['','',''],
  ]
}

player.value = 'X'
</script>

<template>
  <main class="mt-8 text-center">
    <h1 class="mb-8 text-3xl font-bold uppercase">Tic Tac Toe</h1>
    <h3 class="text-xl mb-4"> Player {{ player }}'s turn</h3>
    <section class="flex flex-col items-center mb-8">
      <div v-for="(row, x) in board" :key="x" class="flex">
        <div v-for="(cell, y) in row" :key="y" @click="MakeMove(x, y)"
             class="border-2 w-20 h-20 hover:bg-gray-200 flex items-center justify-center border-slate-700 text-4xl cursor-pointer">
          {{ cell === 'X' ? 'X' : cell === 'O' ? 'O' : ''}}
        </div>
      </div>
    </section>
      <h2 v-if="winner" class="font-bold text-2xl mb-8">
        Player "{{ winner}}" won the game
      </h2>
    <button @click="ResetGame" class="text-sm bg-red-50 border-2 border-red-500 rounded-md text-red-500 py-0.5 px-3 font-medium hover:text-white hover:bg-red-500 duration-300">
      Reset Game
    </button>
  </main>
</template>
