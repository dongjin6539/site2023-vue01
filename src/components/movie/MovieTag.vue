<template>
  <div class="movie__tag">
    <div>
      <button
        v-for="(tag, index) in movieTags"
        :key="index"
        @click="btnClick(tag.name)"
        :class="{ active: tag.name === activeTag }"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movieTags: [
        {
          name: "최신 영화",
          url: "https://api.themoviedb.org/3/movie/now_playing",
        },
        {
          name: "인기 영화",
          url: "https://api.themoviedb.org/3/movie/popular",
        },
        {
          name: "영화 순위",
          url: "https://api.themoviedb.org/3/movie/top_rated",
        },
        {
          name: "개봉 예정",
          url: "https://api.themoviedb.org/3/movie/upcoming",
        },
        { name: "TV 인기", url: "https://api.themoviedb.org/3/tv/popular" },
        { name: "TV 순위", url: "https://api.themoviedb.org/3/tv/top_rated" },
        {
          name: "영화 트렌드",
          url: "https://api.themoviedb.org/3/trending/movie/day",
        },
        {
          name: "TV 트렌드",
          url: "https://api.themoviedb.org/3/trending/tv/day",
        },
      ],
      activeTag: "",
    };
  },
  methods: {
    btnClick(tagName) {
      const clickedTag = this.movieTags.find((tag) => tag.name === tagName);
      if (clickedTag) {
        this.activeTag = clickedTag.name;
        this.$emit("search", clickedTag.url);
      }
    },
  },
};
</script>
