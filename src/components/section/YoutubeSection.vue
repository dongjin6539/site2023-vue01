<template>
  <section id="youtubeSection" :class="attr">
    <div class="youtube__inner container">
      <div class="youtube__text">
        <h3>추천 유튜브 영상</h3>
        <p>
          유튜브를 통해 다양한 농구 영상을 볼 수 있습니다.
          <br />
          구독과 좋아요! 부탁드립니다.
        </p>
        <router-link to="/youtube" class="button-green">
          자세히 보기
        </router-link>
      </div>
      <div class="youtube__item">
        <div class="youtube">
          <img src="@/assets/images/youtube/youtube01.png" alt="유튜브1" />
          <!-- <iframe
            width="400"
            height="250"
            src="https://www.youtube.com/embed/QsCB9Ci9J7Q"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe> -->
        </div>
        <div class="youtube">
          <img src="@/assets/images/youtube/youtube02.png" alt="유튜브2" />
          <!-- <iframe
            width="400"
            height="250"
            src="https://www.youtube.com/embed/R7u1qlHO-cQ"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe> -->
        </div>
        <div class="youtube">
          <img src="@/assets/images/youtube/youtube03.png" alt="유튜브3" />
          <!-- <iframe
            width="400"
            height="250"
            src="https://www.youtube.com/embed/DbuVTHUJWFk"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe> -->
        </div>
        <div class="youtube">
          <img src="@/assets/images/youtube/youtube04.png" alt="유튜브4" />
          <!-- <iframe
            width="400"
            height="250"
            src="https://www.youtube.com/embed/49Z-OGD7D6k"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe> -->
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
// youtube__wrap
.youtube__inner {
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
  .youtube__item {
    @include flex-between;
    margin-top: 50px;
    position: absolute;
    .youtube {
      width: 400px;
      margin-right: 20px;
      iframe {
        width: 100%;
        border-radius: 20px;
      }
    }
  }
}

// youtube__page
.youtube__slider {
  display: none;
}
.youtube__search {
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
    @include button(#00c183, #fff);
    border-radius: 50px;
  }
}
.youtube__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    li {
      a {
        border: 1px solid #00c183;
        padding: 10px 20px;
        margin: 0 10px;
        color: #00c183;
      }
    }
  }
}
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;
    li {
      width: 24%;
      margin-bottom: 4%;
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
</style>
