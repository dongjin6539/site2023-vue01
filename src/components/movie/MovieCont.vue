<template>
  <div class="movie__cont container">
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="
              movie.poster_path
                ? `https://image.tmdb.org/t/p/w500${movie.poster_path}`
                : require('@/assets/images/movie/noImage.png')
            "
            :alt="movie.title"
          />
          <span class="title">{{ movie.title || movie.name }}</span>
          <span class="star">{{ movie.vote_average }}</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 100px;
    li {
      width: 24%;
      margin-bottom: 4%;
      position: relative;
      &:hover .title {
        text-decoration: underline;
        text-underline-position: under;
      }
      span {
        display: block;
        margin: 4px 0;
      }
      .title {
        font-size: 20px;
        display: block;
        padding: 3px 0;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .star {
        position: absolute;
        left: 10px;
        top: 10px;
        width: 50px;
        height: 50px;
        background-image: url(@/assets/images/movie/star.png);
        background-repeat: no-repeat;
        background-position: center;
        text-align: center;
        line-height: 54px;
        border-radius: 50%;
        font-size: 12px;
      }
    }
  }
}
</style>
