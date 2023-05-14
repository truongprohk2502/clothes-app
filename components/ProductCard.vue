<script setup lang="ts">
interface IProps {
  id: string;
  title: string;
  image: string;
}

const { id, title, image } = defineProps<IProps>();
</script>

<template>
  <div class="card text-center">
    <img :src="`${image}`" class="thumb" />
    <p class="font-bold text-gray-500 m-4 truncate">{{ title }}</p>
    <NuxtLink :to="`/products/${id}`">
      <p
        class="bg-[#12b488] text-white px-3 py-2 rounded-md text-sm text-white my-4"
      >
        View Details
      </p>
    </NuxtLink>
  </div>
</template>

<style scoped>
.thumb {
  max-height: 120px;
  max-width: 70%;
  margin: 0 auto;
}
</style>
