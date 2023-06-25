<template>
  <div class="unsplash__slider">
    <swiper
      :slides-per-view="3"
      :space-between="30"
      navigation
      :pagination="{ clickable: true }"
      :autoplay="{
        delay: 2500,
        disableOnInteraction: false,
      }"
      :effect="'coverflow'"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
    >
      <swiper-slide v-for="(unsplash, index) in unsplashs" :key="index">
        <a :href="`http://unsplash.com/photos/${unsplash.id}`" target="_blank">
          <img
            :src="unsplash.urls.regular"
            :alt="unsplash.alt_description"
            style="width: 1200px; height: 500px; object-fit: cover"
          />
        </a>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
// import Swiper core and required modules
import { Swiper, SwiperSlide } from "swiper/vue";
import SwiperCore, {
  Navigation,
  Pagination,
  Autoplay,
  EffectCoverflow,
} from "swiper";

// Import Swiper styles
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/effect-coverflow";

SwiperCore.use([Navigation, Pagination, Autoplay, EffectCoverflow]);

export default {
  props: {
    unsplashs: {
      type: Array,
      required: true,
    },
  },
  components: {
    Swiper,
    SwiperSlide,
  },
};
</script>
