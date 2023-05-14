<script setup lang="ts">
const {
  params: { id },
} = useRoute();

interface IProductDetail {
  id: string;
  title: string;
  price: number;
}

const { data: product } = await useFetch<IProductDetail>(
  "https://fakestoreapi.com/products/" + id,
  { key: id as string }
);

definePageMeta({
  layout: "products",
});
</script>

<template>
  <div v-if="product">
    <p>{{ product.title }}</p>
    <p>{{ product.price }}</p>
    <p>{{ product.id }}</p>
  </div>
</template>
