<template>
  <div class="dim">      
    <img :src="imgSrc" :alt="imgAlt" class="w-100 db tc outline black-10" />
    <p class="f7 tl ttu pt3 mb0 tracked-mega mt0 code lh-copy measure gray">NOV 5, 2019</p>
    <p class="f7 tl ttu tracked-mega mt0 code lh-copy measure black">{{artist}}</p>
  </div>                    
</template>

<script>
export default {
  props: ["imgSrc", "imgAlt", "title", "artist"]
};
</script>
