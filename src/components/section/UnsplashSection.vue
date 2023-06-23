<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner container">
      <div class="unsplash__text">
        <h3>추천 이미지</h3>
        <p>다양한 농구 이미지를 제공하고 있습니다.</p>
        <router-link to="/unsplash" class="button-blue"
          >자세히 보기</router-link
        >
      </div>
      <div class="unsplash__item">
        <div class="unsplash">
          <img
            src="@/assets/images/unsplash/unsplash01.png"
            alt="언스플래쉬1"
          />
        </div>
        <div class="unsplash">
          <img
            src="@/assets/images/unsplash/unsplash02.png"
            alt="언스플래쉬2"
          />
        </div>
        <div class="unsplash">
          <img
            src="@/assets/images/unsplash/unsplash03.png"
            alt="언스플래쉬3"
          />
        </div>
        <div class="unsplash">
          <img
            src="@/assets/images/unsplash/unsplash04.png"
            alt="언스플래쉬4"
          />
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

// unsplash__wrap
.unsplash__inner {
  height: 600px;
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
  .unsplash__item {
    @include flex-between;
    margin-top: 50px;
    position: absolute;
    .unsplash {
      width: 400px;
      margin-right: 20px;
      img {
        width: 100%;
      }
    }
  }
}

// unsplash__page
.unsplash__slider {
  display: none;
}
.unsplash__search {
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
    @include button(#4857ec, #fff);
    border-radius: 50px;
  }
}
.unsplash__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    li {
      a {
        border: 1px solid #4857ec;
        padding: 10px 20px;
        margin: 0 10px;
        color: #4857ec;
      }
    }
  }
}
.unsplash__cont {
  ul {
    column-count: 4;
    li {
      margin-bottom: 20px;
    }
  }
}
</style>
