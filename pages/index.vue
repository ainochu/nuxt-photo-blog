<template>
  <article>
    <header class="bg-white black-80 tc pv4 avenir">
      <h1 class="mt2 mb0 baskerville i fw1 f1">El rinconciti de Ainowis</h1>
      <h2 class="mt2 mb0 f6 fw4 ttu tracked">Fotos chupi postu guapis</h2>
      <nav class="bt bb tc mw7 center mt4">
        <a class="f6 f5-l link bg-animate black-80 dib pa3 ph4-l" href="/">Home</a>
        <a class="f6 f5-l link bg-animate black-80 dib pa3 ph4-l" href="/about">About me</a>
      </nav>
    </header>
    <div class="cf pa8 pl6">
      <nuxt-link :to="`/albums/${item.id}`" v-for="item in items" :key="item.id" class="db">
        <album-card
          :imgSrc="item.imgSrc"
          :imgAlt="item.imgAlt"
          :title="item.title"
          :artist="item.artist"
        />
      </nuxt-link>
    </div>
  </article>
</template>

<script>
import AlbumCard from "../components/card";
import Carousel from "../components/carousel";
import { items } from "../services/data";

export default {
  data() {
    return {
      items
    };
  },
  computed: {
    carouselImages() {
      return this.items.map(item => item.imgSrc);
    }
  },
  components: {
    AlbumCard,
    Carousel
  }
};
</script>
