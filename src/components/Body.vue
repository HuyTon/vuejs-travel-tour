<template>
  <div class="page-body">
    <div class="body-part">
      <div class="body-part-content">
        <nav class="navigation">
          <router-link to="/asia" class="link">Asia</router-link>
          <span class="arrow">&gt;</span>
          <router-link to="/singapore" class="link">Singapore</router-link>
          <span class="arrow">&gt;</span>
          <router-link to="/strenuous-travel-style" class="link"
            >Strenuous Travel Style</router-link
          >
        </nav>
        <h1 class="kanit-extrabold title">Marina Bay Sands Observation</h1>
        <p class="description">
          A great spot for P&R order yourself a drink from the bar and get
          comfortable on one of the day beds that line the impressive 100-metre
          pool.
        </p>
        <div class="itinerary">
          <img
            src="@/assets/itinerary_icon.png"
            alt="Itinerary Icon"
            class="icon"
          />
          <span class="kanit-semibold itienary-text">Itinerary</span>
        </div>
        <div class="itienary-container">
          <div class="slide-container">
            <ItinerarySlider />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ItinerarySlider from "@/components/ItinerarySlider.vue";

export default {
  name: "PageBody",
  components: {
    ItinerarySlider,
  },
};
</script>

<style>
.page-body {
  display: flex;
  justify-content: center; /* Horizontal centering */
  align-items: center; /* Vertical centering */
  width: 100%;
}

.body-part {
  text-align: center;
  border: 1px solid #ccc;
  width: 80%;
  height: 100%;
  background-color: white;
  margin-top: -30px;
  z-index: 2;
}

.body-part-content {
  text-align: left;
  padding: 30px 20px;
}

.navigation {
  font-size: 12px;
  font-weight: 500;
}

.navigation .link {
  text-decoration: none; /* Remove underline from links */
  color: #878484; /* Set link color */
  cursor: pointer;
}

.navigation .arrow {
  padding: 0px 10px;
}

.title {
  font-size: 26px;
  margin-top: 20px;
}

.description {
  font-size: 14px;
  margin-top: 10px;
  font-weight: 500;
}

.icon {
  width: 20px;
  height: 20px;
}

.itienary-text {
  margin-left: 10px;
  font-size: 17px;
}

.itienary-container {
  padding: 20px 25px;
}

.itienary-container .slide-container {
}
</style>
