<template>
  <main>
    <SliderSection attr="slider__wrap section gmarket5" />
    <IntroSection attr="intro__wrap gmarket5 section" />
    <PortSection attr="port__wrap gmarket5 section center bg-blue" />
    <YoutubeSection attr="youtube__wrap gmarket5 section" />
    <UnsplashSection attr="unsplash__wrap gmarket5 section bg-blue" />
    <MovieSection attr="movie__wrap gmarket5 section" />
  </main>
</template>

<script>
import SliderSection from "@/components/section/SliderSection.vue";
import IntroSection from "@/components/section/IntroSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";

export default {
  components: {
    SliderSection,
    IntroSection,
    PortSection,
    YoutubeSection,
    UnsplashSection,
    MovieSection,
  },
};
</script>
