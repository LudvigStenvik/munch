<template>
  <div class="image-display">
    <img :src="imageUrl" alt="Processed Image" />
  </div>
</template>

<script>
export default {
  name: "ImageDisplay",
  props: {
    imageUrl: String,
  },
};
</script>