<template>
  <div class="movie__slider">
    <swiper
      :modules="modules"
      :slides-per-view="3"
      :space-between="30"
      navigation
      :pagination="{ clickable: true }"
      :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide v-for="(movie, index) in movies" :key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w1280${movie.backdrop_path}`"
            :alt="movie.title"
          />
        </a>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
// import Swiper core and required modules
import { Navigation, Pagination, A11y, Autoplay } from "swiper";

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, Pagination, A11y, Autoplay],
    };
  },
};
</script>
