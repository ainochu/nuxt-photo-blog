<template>
  <div class="mw5 mw6-ns center pt4">
    <img :src="currentImage"/>
    <div class="flex items-center justify-center pa4">
      <button
        @click="goPrevious"
        class="f5 no-underline black bg-animate hover-bg-black hover-white inline-flex items-center pa3 ba border-box mr4"
      >
        <span class="pl1">Previous</span>
      </button>
      <button
        @click="goNext"
        class="f5 no-underline black bg-animate hover-bg-black hover-white inline-flex items-center pa3 ba border-box"
      >
        <span class="pr1">Next</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentImage: null,
      currentImageIndex: 0
    };
  },
  props: ["carouselImages"],
  mounted() {
    this.currentImage = this.carouselImages[this.currentImageIndex];
  },
  methods: {
    goNext(event) {
      this.currentImageIndex =
        (this.currentImageIndex + 1) % this.carouselImages.length;
      this.currentImage = this.carouselImages[this.currentImageIndex];
    },
    goPrevious(event) {
      this.currentImageIndex =
        (this.currentImageIndex - 1 + this.carouselImages.length) %
        this.carouselImages.length;
      this.currentImage = this.carouselImages[this.currentImageIndex];
    }
  }
};
</script>
