<script setup>
defineProps({
  id: Number,
  img: String,
  title: String,
  price: Number,
  onClickDelete: Function
})

const emit = defineEmits('onClickRemove')
</script>

<template>
  <div class="relative flex w-full border border-slate-100 rounded-xl p-4 gap-4">
    <img :src="img" class="w-16 h-16" :alt="title" />

    <div class="flex flex-col w-full flex-1">
      <p>{{ title }}</p>
      <div class="flex justify-between mt-5">
        <span class="font-bold flex-1">{{ price }} руб.</span>
        <img
          @click="emit('onClickRemove')"
          class="cursor-pointer opacity-30 hover:opacity-100 transition"
          src="/close.svg"
          alt="Close"
        />
      </div>
    </div>
  </div>
</template>
