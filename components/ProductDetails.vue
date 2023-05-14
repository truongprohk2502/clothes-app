<script setup lang="ts">
interface IProps {
  title: string;
  image: string;
  price: number;
  description: string;
}

const { image, title, price, description } = defineProps<IProps>();
</script>

<template>
  <div class="card">
    <div class="grid grid-cols-2 gap-10">
      <div class="p-7">
        <img :src="`${image}`" class="mx-auto my-7" />
      </div>
      <div class="p-7">
        <h2 class="text-4xl my-7">{{ title }}</h2>
        <p class="text-xl my-7">Price - ${{ price }}</p>
        <h3 class="font-bold border-b-2 mb-4 pb-2">Product description:</h3>
        <p class="mb-7">{{ description }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
img {
  max-width: 400px;
}
</style>
