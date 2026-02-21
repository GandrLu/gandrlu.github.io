<script setup>
import { ref } from 'vue'

defineProps({
  aId: String,
  title: String,
  text: String,
  listing: Array,
  reference: Object,
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
  <a v-if="reference" :href="reference.link" target="_blank">{{ reference.text }}</a>
  <br />
  <div v-if="imgs">
    <div v-for="(img, index) in imgs" class="responsive">
      <div class="gallery">
        <img :key="index" :src="img + '?url'" alt="Article Image" :class="img.includes('portrait') ? 'portraitFormatImg' : ''">
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

<style scoped>
a {
  display: block;
}
</style>
