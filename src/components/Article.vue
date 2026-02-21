<script setup>
import { ref } from 'vue'

defineProps({
  aId: String,
  title: String,
  text: String,
  listing: Array,
  reference: String,
  imgs: Array,
  vVids: Array
})

const count = ref(0)
</script>

<template>
  <h2 :id="aId">{{ title }}</h2>
  <p>{{ text }}</p>
  <ul v-if="listing">
    <li v-for="(item, index) in listing" :key="index">{{ item }}</li>
  </ul>
  <p v-if="reference">Further insights: <a :href="reference" target="_blank">{{ reference }}</a></p>
  <br>
  <div v-if="imgs">
    <div v-for="(img, index) in imgs" class="responsive">
      <div class="gallery">
        <img :key="index" :src="img" alt="Article Image">
      </div>
    </div>
  </div>

  <div v-if="vVids">
    <div v-if="vVids.length > 1" v-for="(url) in vVids" class="responsive">
      <div class="gallery">
        <iframe :src="url" width="640" height="360" frameborder="0"
          allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
    <div v-else>
      <iframe v-for="(url) in vVids" :src="url" width="640" height="360" frameborder="0"
        allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
    </div>
  </div>

  <div class="clearfix"></div>
</template>

<style scoped></style>
