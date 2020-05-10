<template>
  <article>
    <header class="nav-bar">
      <nav class="db dt-l w-100 border-box pa3 ph5-l">
        <a
          class="db dtc-l v-mid mid-gray link dim w-100 w-25-l tc tl-l mb2 mb0-l"
          href="#"
          title="Home"
        >
          <img
            src="https://live.staticflickr.com/65535/49867578281_87a924464b.jpg"
            class="dib w-50 h100 br-100"
          />
        </a>
        <div class="db dtc-l v-mid w-100 w-75-l tc tr-l ttu code lh-copy measure b">
          <a class="link dim dark-gray f6 pl3 ttu tracked-mega mt0" href="#" title="Home">Home</a>
          <a class="link dim dark-gray f6 pl3 ttu tracked-mega mt0" href="#" title="Blog">About me</a>
          <a class="link dim dark-gray f6 pl3 ttu tracked-mega mt0" href="#" title="Press">Blog</a>
          <a class="link dim dark-gray f6 pl3 ttu tracked-mega mt0" href="#" title="Contact">Contact</a>
        </div>
      </nav>
    </header>
    <p class="pt5 tc f3 ttu tracked-mega mt0">LATEST POSTS</p>
    <div class="flex flex-wrap cf pa3 card-full">
      <nuxt-link
        :to="`/albums/${item.id}`"
        v-for="item in items"
        :key="item.id"
        class="link w-60 w-35-m w-30-l pa2 db"
      >
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
