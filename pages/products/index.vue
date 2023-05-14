<script setup lang="ts">
interface IProduct {
  id: string;
  title: string;
}

const { data: products } = await useFetch<IProduct[]>(
  "https://fakestoreapi.com/products"
);

definePageMeta({
  layout: "products",
});
</script>

<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="item in products">
        <NuxtLink :to="`/products/${item.id}`">{{ item.title }}</NuxtLink>
      </div>
    </div>
  </div>
</template>
