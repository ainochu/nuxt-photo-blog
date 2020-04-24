<template>
  <div class="fl w-60 w-35-m w-30-l pa2">
    <div class="dim tc">
      <img :src="imgSrc" :alt="imgAlt" class="w-100 db outline black-10" />
      <dl class="mt2 f6 lh-copy">
        <dt class="clip">Title</dt>
        <dd class="ml0 black truncate w-100">{{title}}</dd>
        <dt class="clip">Artist</dt>
        <dd class="ml0 gray truncate w-100">{{artist}}</dd>
      </dl>
    </div>
  </div>
</template>

<script>
export default {
  props: ["imgSrc", "imgAlt", "title", "artist"]
};
</script>
