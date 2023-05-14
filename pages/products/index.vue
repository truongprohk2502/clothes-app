<script setup lang="ts">
interface IProduct {
  id: string;
  title: string;
  image: string;
  description: string;
  price: number;
}

const { data: products } = await useFetch<IProduct[]>(
  "https://fakestoreapi.com/products"
);

definePageMeta({
  layout: "products",
});

useHead({
  title: "Nuxt Dojo | Merch",
  meta: [{ name: "description", content: "Nuxt 3 Merch" }],
});
</script>

<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <ProductCard
        v-for="item in products"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :image="item.image"
      />
    </div>
  </div>
</template>
