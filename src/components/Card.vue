<script setup>
import { inject } from 'vue'

const props = defineProps({
  id: Number,
  title: String,
  img: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function
})

// const addToFavorite = inject('addToFavorite')
</script>

<template>
  <div
    class="bg-white relative flex flex-col w-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-xl hover:transform hover:-translate-y-2"
  >
    <!-- <div @click="onClick" class="absolute top-8 left-8">
    </div> -->
    <img
      v-if="onClickFavorite"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="Favorite"
      class="absolute top-8 right-8"
      @click="onClickFavorite"
    />
    <img :src="img" class="w-full" alt="Sneaker" />

    <p>{{ title }}</p>
    <div class="flex justify-between mt-5">
      <div class="flex flex-col gap-2">
        <span class="text-slate-200">Цена:</span>
        <span class="font-bold">{{ price }} руб.</span>
      </div>

      <img
        v-if="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
        @click="onClickAdd"
      />
    </div>
  </div>
</template>
