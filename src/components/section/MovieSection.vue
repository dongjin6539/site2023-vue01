<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner container">
      <div class="movie__text">
        <h3>추천 영화</h3>
        <p>농구를 주제로 한 다양한 영화를 추천드리고 있습니다.</p>
        <router-link to="/movie" class="button-red">자세히 보기</router-link>
      </div>
      <div class="movie__item">
        <div class="movie">
          <img src="@/assets/images/movie/movie01.png" alt="영화1" />
        </div>
        <div class="movie">
          <img src="@/assets/images/movie/movie02.png" alt="영화2" />
        </div>
        <div class="movie">
          <img src="@/assets/images/movie/movie03.png" alt="영화3" />
        </div>
        <div class="movie">
          <img src="@/assets/images/movie/movie04.png" alt="영화4" />
        </div>
        <div class="movie">
          <img src="@/assets/images/movie/movie05.png" alt="영화5" />
        </div>
        <div class="movie">
          <img src="@/assets/images/movie/movie06.png" alt="영화6" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    attr: String,
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";

// movie__wrap
.movie__inner {
  height: 800px;
  h3 {
    font-size: 50px;
    margin-bottom: 40px;
  }
  p {
    font-size: 24px;
    font-weight: 300;
    margin-bottom: 20px;
  }
  a {
    border-radius: 50px;
    margin-bottom: 60px;
  }
  .movie__item {
    @include flex-between;
    margin-top: 50px;
    position: absolute;
    .movie {
      width: 300px;
      margin-right: 20px;
      img {
        width: 100%;
      }
      span {
        display: block;
        margin: 4px 0;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
  }
}

// movie__page
.movie__slider {
  margin-bottom: 100px;
}
.movie__search {
  text-align: center;
  margin-bottom: 50px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    border-radius: 50px;
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#ff3344, #fff);
    border-radius: 50px;
  }
}
.movie__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    button {
      border: 1px solid #ff3344;
      padding: 10px 20px;
      margin: 0 10px;
      color: #ff3344;
      background-color: #fff;
      &:hover {
        background-color: #ff3344;
        color: #fff;
      }
    }
    button.active {
      background-color: #ff3344; /* 선택된 태그의 배경색 */
      color: #ffffff; /* 선택된 태그의 텍스트 색상 */
    }
  }
}
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
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
        display: inline-block;
        padding: 3px 0;
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
