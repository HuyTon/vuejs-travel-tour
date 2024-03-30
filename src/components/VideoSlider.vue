<template>
  <div class="video-slider">
    <div class="slides-container">
      <div
        v-for="(video, index) in videos"
        :key="index"
        class="slide"
        :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
      >
        <video
          :src="video.src"
          controls
          class="video"
          ref="videoElement"
        ></video>
      </div>
    </div>
    <button class="arrow-btn left" @click="prevSlide">
      <span class="circle"><span class="arrow-icon">&lt;</span></span>
    </button>
    <button class="arrow-btn right" @click="nextSlide">
      <span class="circle"><span class="arrow-icon">&gt;</span></span>
    </button>
  </div>
</template>

<script>
export default {
  name: "VideoSlider",
  data() {
    return {
      videos: [
        { src: require("@/assets/videos/video1.mp4") },
        { src: require("@/assets/videos/video2.mp4") },
        { src: require("@/assets/videos/video3.mp4") },
      ],
      currentIndex: 0, // Index of the currently active slide
    };
  },
  methods: {
    nextSlide() {
      if (this.currentIndex < this.videos.length - 1) {
        this.currentIndex++;
      }
    },
    prevSlide() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
  },
};
</script>

<style scoped>
.video-slider {
  position: relative;
  overflow: hidden;
  width: 100%;
}

.slides-container {
  display: flex;
  transition: transform 0.5s ease;
}

.slide {
  flex: 0 0 100%;
}

.video {
  width: 100%;
  height: 300px;
  object-fit: cover; /* Ensure video content fills the container */
}

.arrow-btn {
  position: absolute;
  top: 50%;
  background: transparent;
  border: none;
  color: black;
  cursor: pointer;
  z-index: 1;
}

.arrow-btn.left {
  left: 10px; /* Adjust the position of the left arrow */
}

.arrow-btn.right {
  right: 10px; /* Adjust the position of the right arrow */
}

.circle {
  position: relative;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.arrow-btn.left .arrow-icon {
}

.arrow-btn.right .arrow-icon {
}

.arrow-icon {
  color: black;
  font-size: 11px;
}
</style>
