<template>
  <main class="grid grid-cols-2 gap-8 container">
    <div class="grid grid-cols-4 gap-6">
      <div class="col-span-4 rounded-xl overflow-hidden">
        <img :src="activeImage.image" :alt="activeImage.altText">
      </div>
      <div class="rounded-xl overflow-hidden border-2 relative cursor-pointer" :class="image.active && 'border-orange-500'" v-for="image in images" :key="image.id" @click="()=>changeImage(image)">
        <div class="absolute inset-0 bg-white/50" v-if="image.active"></div>
        <img :src="image.thumbnail" :alt="image.altText" />
      </div>
    </div>
  </main>
</template>

<script setup>
import { reactive, ref } from "vue";
const images = reactive([
  {
    id: 1,
    image:require("@/assets/products/product-1/product.jpg"),
    thumbnail: require("@/assets/products/product-1/product-thumbnail.jpg"),
    altText: "product 1",
    active: true,
  },
  {
    id: 2,
    image:require("@/assets/products/product-2/product.jpg"),
    thumbnail: require("@/assets/products/product-2/product-thumbnail.jpg"),
    altText: "product 2",
    active: false,
  },
  {
    id: 3,
    image:require("@/assets/products/product-3/product.jpg"),
    thumbnail: require("@/assets/products/product-3/product-thumbnail.jpg"),
    altText: "product 3",
    active: false,
  },
  {
    id: 4,
    image:require("@/assets/products/product-4/product.jpg"),
    thumbnail: require("@/assets/products/product-4/product-thumbnail.jpg"),
    altText: "product 4",
    active: false,
  },
]);
const activeImage = ref(images.find(image=> image.active===true));
const changeImage = (imgObj)=> {
  activeImage.value.active = false;
  imgObj.active = true;
  activeImage.value = imgObj;
}
// console.log(activeImage);
</script>
