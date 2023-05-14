<script setup lang="ts">
const {
  params: { id },
} = useRoute();

interface IProductDetail {
  id: string;
  title: string;
  image: string;
  description: string;
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
  <ProductDetails
    v-if="product"
    :title="product.title"
    :image="product.image"
    :description="product.description"
    :price="product.price"
  />
</template>
