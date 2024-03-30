<template>
  <header class="app-header">
    <div class="header-part header-part-left"></div>
    <div class="header-part header-part-center">
      <VideoSlider />
    </div>
    <div class="header-part header-part-right"></div>
  </header>
</template>

<script>
import VideoSlider from "@/components/VideoSlider.vue";

export default {
  name: "AppHeader",
  components: {
    VideoSlider,
  },
};
</script>

<style scoped>
.app-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 300px;
}

.header-part {
  height: 100%;
}

.header-part-left {
  background-image: url("~@/assets/left-header.png");
  background-size: cover; /* Cover the entire area */
  background-position: right top; /* Adjust this as needed */
  width: 10%;
}

.header-part-right {
  background-image: url("~@/assets/right-header.png");
  background-size: cover; /* Cover the entire area */
  background-position: left top; /* Adjust this as needed */
  width: 10%;
}

.header-part-center {
  padding: 0px 5px 0px 5px;
}
</style>
