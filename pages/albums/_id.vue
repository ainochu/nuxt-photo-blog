<template>
  <main>
    <p>Official album space {{$route.params.id}}</p>
    <album-card
      :imgSrc="album.imgSrc"
      :imgAlt="album.imgAlt"
      :title="album.title"
      :artist="album.artist"
    />
  </main>
</template>

<script>
import AlbumCard from "../../components/card";
import { items } from "../../services/data";

export default {
  asyncData({ $axios, params, error }) {
    const album = items.find(item => item.id === params.id);

    if (album) {
      return {
        album
      };
    } else {
      error({ statuscode: 404, message: "Not found" });
    }
  },
  components: {
    AlbumCard
  }
};
</script>
