<template>
  <ContTitle title="unsplash" />
  <UnsplashSlider :unsplashs="unsplashs" />
  <UnsplashSerach :onSearch="search" />
  <UnsplashTag :onSearch="search" />
  <UnsplashCont :unsplashs="unsplashs" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSerach from "@/components/unsplash/UnsplashSerach.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSerach,
    UnsplashTag,
    UnsplashCont,
  },
  setup() {
    const unsplashs = ref([]);

    const TopUnsplashs = async () => {
      await fetch(
        "https://api.unsplash.com/photos?client_id=8KxfRej-WhG3bLJet9sMULT9u09loxyVYjMsOdZVKTg&per_page=30"
      )
        .then((response) => response.json())
        .then((result) => {
          unsplashs.value = result;
        })
        .catch((error) => console.log("error", error));
    };

    const search = async (query) => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=8KxfRej-WhG3bLJet9sMULT9u09loxyVYjMsOdZVKTg&per_page=30&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          unsplashs.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    TopUnsplashs();

    return {
      unsplashs,
      search,
      TopUnsplashs,
    };
  },
};
</script>
