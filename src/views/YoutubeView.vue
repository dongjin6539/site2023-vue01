<template>
  <ContTitle title="youtube" />
  <YoutubeSlider :youtubes="youtubes" />
  <YoutubeSearch :onSearch="search" />
  <YoutubeTag :onSearch="search" />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },
  setup() {
    const youtubes = ref([]);

    const TopYoutubes = async () => {
      await fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=32&q=농구&type=video&videoDuration=medium&key=AIzaSyCP7j_dh-rc1KAc4FUEHCGNU0MZhPsM_Rw"
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };

    const search = async (query) => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=32&q=${query}&type=video&videoDuration=medium&key=AIzaSyCP7j_dh-rc1KAc4FUEHCGNU0MZhPsM_Rw`
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items;
        })
        .catch((error) => console.log(error));
    };

    TopYoutubes();

    return {
      youtubes,
      search,
      TopYoutubes,
    };
  },
};
</script>
