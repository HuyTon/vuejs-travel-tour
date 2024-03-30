<template>
  <div class="itinerary-slider">
    <div class="slide" v-for="(item, index) in arr" :key="index">
      <div class="content-container">
        <div class="image-slider">
          <Carousel :items-to-show="1">
            <slide
              v-for="(image, imgIndex) in item.images"
              :key="imgIndex"
              class="image"
              alt="Slide Image"
            >
              <img
                :src="require(`@/assets/images/slides/${image}`)"
                :key="imgIndex"
                class="image"
                alt="Slide Image"
              />
            </slide>
            <template #addons>
              <Navigation />
              <Pagination />
            </template>
          </Carousel>
        </div>
        <div class="text-content">
          <span class="kanit-extrabold title-text">{{ item.title }}</span>
          <span class="kanit-extrabold title-description">{{
            item.title_description
          }}</span>
          <p class="description">{{ item.description }}</p>
          <a href="#" class="show-more">Show more</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

export default defineComponent({
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      arr: [
        {
          title: "Day 1",
          title_description: "See the largest indoor water fall in the world",
          description:
            "Just how much mind-boggling can be packed into a 14-day holiday? Well we'll tell you. Our hot adventure pack serious punch on a journey city Singapore and Malaysia.",
          images: ["1.jpeg", "2.jpeg"],
        },
        {
          title: "Day 2",
          title_description: "Two giant conservatories",
          description:
            "Two giant conservatories rise beside Marina Bay like futuristic shells, one home to ancient olive trees, the other to a towering, tropical mountain. To the north are the Supertrees: futuristic...",
          images: ["3.jpeg", "4.jpeg"],
        },
        {
          title: "Day 3",
          title_description: "Singapore's 21st-century botanical garden",
          description:
            "Singapore's 21st-century botanical garden is a $1 billion, 101-hectare.",
          images: ["5.jpeg", "6.jpeg"],
        },
      ],
    };
  },
});
</script>

<style scoped>
.itinerary-slider {
  display: flex;
  flex-wrap: wrap;
  overflow-y: auto;
}

.slide {
  width: 100%;
  margin-bottom: 5px;
  box-sizing: border-box;
  overflow: hidden;
}

.content-container {
  display: flex; /* Display image slider and text content in a row */
}

.image-slider {
  height: 150px;
  width: 200px;
  overflow: hidden;
}

.image {
  height: 150px;
  width: 200px;
  object-fit: cover;
}

.text-content {
  flex: 1; /* Take up remaining space */
  padding: 15px 25px;
  position: relative; /* Position relative for absolute positioning */
}

.title-text {
  font-weight: bold;
}

.title-description {
  margin-left: 20px;
}

.description {
  color: #878484;
  text-align: justify;
}

.show-more {
  position: absolute;
  bottom: 0;
  left: 25px;
  text-decoration: underline;
  font-size: 14px;
  color: #1f6f5c;
  font-weight: 500;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}

/* Media queries for tablet and desktop */
@media (min-width: 768px) {
  .slide {
    width: 100%; /* One slide per row */
  }
}

/* Media queries for mobile devices */
@media (max-width: 767px) {
  .content-container {
    flex-direction: column; /* Display image slider and text content in a column */
  }

  .image-slider,
  .text-content {
    width: 100%; /* Full width for mobile devices */
  }

  .image-slider {
    height: 150px; /* Adjust image slider height */
    margin-bottom: 10px; /* Add spacing between image sliders */
  }

  .text-content {
    padding: 15px; /* Adjust padding for text content */
  }
}
</style>
