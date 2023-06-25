<template>
  <ContTitle title="movies" />
  <MovieSlider :movies="movies" />
  <MovieSearch :onSearch="search" />
  <MovieTag :onSearch="tags" />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },

  setup() {
    const movies = ref([]);

    const TopMovies = async () => {
      await fetch(
        `https://api.themoviedb.org/3/movie/popular?api_key=d437b67f2b55e3f176bbe6232a79ad1b&language=ko-KR`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log("error", error));
    };

    const search = async (query) => {
      await fetch(
        `https://api.themoviedb.org/3/search/movie?api_key=d437b67f2b55e3f176bbe6232a79ad1b&language=ko-KR&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    const tags = async (query) => {
      await fetch(
        `${query}?api_key=d437b67f2b55e3f176bbe6232a79ad1b&language=ko-KR`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    TopMovies();

    return {
      movies,
      search,
      tags,
      TopMovies,
    };
  },
};
</script>
