<script setup>
import { ref } from "vue";

// Define reactive reference for current image
const setImage = ref("img/product-1.jpg");

// Define array of images
const images = [
  {
    thumb: "img/product-1.jpg",
    full: "img/product-1.jpg",
  },
  {
    thumb: "img/product-2.jpg",
    full: "img/product-2.jpg",
  },
  {
    thumb: "img/product-3.jpg",
    full: "img/product-3.jpg",
  },
  {
    thumb: "img/product-4.jpg",
    full: "img/product-4.jpg",
  },
];

// Function to set full image when thumbnail is clicked
function showFullImage(image) {
  setImage.value = image.full;
}
</script>

<template>
  <div class="mt-10 ms-10">
    <div class="flex space-x-3">
      <!-- Loop through images to display thumbnails -->
      <img
        class="cursor-pointer w-32"
        v-for="img in images"
        :src="img.thumb"
        :key="img.thumb"
        @click="showFullImage(img)"
      />
    </div>

    <div class="mt-10">
      <!-- Display the full image -->
      <img class="shadow-xl rounded-xl" :src="setImage" alt="" />
    </div>
  </div>
</template>
