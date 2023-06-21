<template>
  <section id="sliderSection" :class="attr">
    <div class="slider__inner">
      <h2 class="blind">배너 슬라이드</h2>
      <swiper
        :modules="modules"
        :slides-per-view="1"
        :space-between="50"
        navigation
        :pagination="{ clickable: true }"
        :autoplay="{
          delay: 2500,
          disableOnInteraction: false,
        }"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide v-for="(slider, index) in sliders" :key="index">
          <div class="slider__img">
            <div class="slider s1 container">
              <div class="text">
                <h3 v-html="slider.title"></h3>
                <p v-html="slider.desc"></p>
                <a href="#" class="more button-blue">더 알아보기</a>
              </div>
              <div class="img" aria-label="hidden">
                <img :src="slider.iconImage1" :alt="slider.title" />
                <img :src="slider.iconImage2" :alt="slider.title" />
                <img :src="slider.iconImage3" :alt="slider.title" />
              </div>
              <div class="circle" aria-label="hidden">
                <span class="circle c1"></span>
                <span class="circle c2"></span>
                <span class="circle c3"></span>
                <span class="circle c4"></span>
                <span class="circle c5"></span>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
      <!-- <div class="slider__btn">
        <a href="#" class="left"><span class="ir">이전이미지</span></a>
        <a href="#" class="right"><span class="ir">다음이미지</span></a>
      </div>
      <div class="slider__dot">
        <a href="#" class="dot active"><span class="ir">1번 이미지</span></a>
        <a href="#" class="dot"><span class="ir">2번 이미지</span></a>
        <a href="#" class="dot"><span class="ir">3번 이미지</span></a>
      </div> -->
    </div>
  </section>
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
  data: function () {
    return {
      sliders: [
        {
          title: "New<br />portfolio",
          desc: "빛나는 재능은 노력의 결실입니다.<br />열심히 노력하고 사랑하는 일에는 늘 성공의 길이 열립니다.",
          iconImage1: "./assets/images/slider/sliderIcon12.png",
          iconImage2: "./assets/images/slider/sliderIcon2.png",
          iconImage3: "./assets/images/slider/sliderIcon3.png",
        },
        {
          title: "New<br />portfolio",
          desc: "빛나는 재능은 노력의 결실입니다.<br />열심히 노력하고 사랑하는 일에는 늘 성공의 길이 열립니다.",
          iconImage1: "./assets/images/slider/sliderIcon12.png",
          iconImage2: "./assets/images/slider/sliderIcon2.png",
          iconImage3: "./assets/images/slider/sliderIcon3.png",
        },
        {
          title: "New<br />portfolio",
          desc: "빛나는 재능은 노력의 결실입니다.<br />열심히 노력하고 사랑하는 일에는 늘 성공의 길이 열립니다.",
          iconImage1: "./assets/images/slider/sliderIcon12.png",
          iconImage2: "./assets/images/slider/sliderIcon2.png",
          iconImage3: "./assets/images/slider/sliderIcon3.png",
        },
      ],
    };
  },
  props: {
    attr: String,
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

<style lang="scss">
// slider__wrap
.slider__inner {
  position: relative;
  .slider__img {
    .slider {
      .text {
        h3 {
          font-size: 110px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1;
          margin-bottom: 40px;
          padding-top: 100px;
        }
        p {
          font-size: 24px;
          line-height: 1.3;
          margin-bottom: 50px;
        }
        .more {
          font-size: 18px;
          margin-bottom: 100px;
        }
      }
      .img {
        position: absolute;
        right: 0;
        top: 0;
        width: 600px;
        height: 600px;
        background-image: url(@/assets/images/slider/sliderIconBg.png);
        background-size: cover;
        img {
          &:nth-child(1) {
            position: absolute;
            width: 300px;
            left: 10px;
            top: 30px;
          }
          &:nth-child(2) {
            position: absolute;
            width: 300px;
            right: 0;
            bottom: 140px;
          }
          &:nth-child(3) {
            position: absolute;
            width: 300px;
            left: 30px;
            bottom: 0;
          }
        }
      }
      .circle {
        span {
          display: block;
          position: absolute;
          left: 50%;
          top: 50%;
          width: 20px;
          height: 20px;
          border-radius: 50%;
        }
        span:nth-child(1) {
          background-color: var(--button_blue);
          left: -10%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(2) {
          background-color: var(--button_green);
          top: 10%;
          left: 40%;
          width: 40px;
          height: 40px;
        }
        span:nth-child(3) {
          background-color: var(--button_green);
          left: 100%;
          top: 20%;
        }
        span:nth-child(4) {
          background-color: var(--button_red);
          left: 25%;
          top: 15%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(5) {
          background-color: var(--button_blue);
          left: 90%;
          top: 80%;
          width: 30px;
          height: 30px;
        }
      }
    }
  }
  .slider__btn {
    > a {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 22px;
      height: 40px;
      transition: opacity 0.3s;

      &:hover {
        opacity: 0.5;
      }
    }
    .left {
      left: 20px;
      background-image: url(@/assets/images/slider/slider__left.png);
    }
    .right {
      right: 20px;
      background-image: url(@/assets/images/slider/slider__right.png);
    }
  }
  .slider__dot {
    position: absolute;
    left: 50%;
    bottom: -80px;
    transform: translateX(-50%);
    a {
      display: inline-block;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      margin: 0 5px;
      border: 4px solid #ff3344;
      background-color: #ff3344;
      box-shadow: 0 0 0 3px transparent;
      &.active {
        box-shadow: 0 0 0 3px #ff3344;
        border-width: 4px;
        background-color: #fff;
      }
    }
  }
}
</style>
