<template>
  <section id="portSection" :class="attr">
    <h3>농구 유명인</h3>
    <p>각 리그 별 농구 유명인입니다.</p>
    <div class="port__inner container">
      <div class="port__btn">
        <button class="active">NBA</button>
        <button>WNBA</button>
        <button>KBL</button>
        <button>WKBL</button>
      </div>
      <div class="port__cont">
        <div class="port" v-for="(text, index) in texts" :key="index">
          <figure class="port__header">
            <img :src="text.portImg" alt="포트폴리오1" />
          </figure>
          <div class="port__body">
            <span>
              <img :src="text.iconImg" alt="멤버1" />
            </span>
            <div>
              <h4>{{ text.title }}</h4>
              <router-link to="/port">{{ text.desc }}</router-link>
            </div>
          </div>
        </div>
        <!-- <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port01.png" alt="포트폴리오1" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember01.svg" alt="멤버1" />
            </span>
            <div>
              <h4>마이클 조던</h4>
              <Link to="/port">Michael Jordan</Link>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port02.png" alt="포트폴리오2" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember02.svg" alt="멤버2" />
            </span>
            <div>
              <h4>르브론 제임스</h4>
              <Link to="/port">Lebron James</Link>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port03.png" alt="포트폴리오3" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember03.svg" alt="멤버3" />
            </span>
            <div>
              <h4>코비 브라이언트</h4>
              <Link to="/port">Kobe Bryant</Link>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port04.png" alt="포트폴리오4" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember04.svg" alt="멤버4" />
            </span>
            <div>
              <h4>케빈 듀란트</h4>
              <Link to="/port">Kevin Durant</Link>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port05.png" alt="포트폴리오5" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember05.svg" alt="멤버5" />
            </span>
            <div>
              <h4>스테판 커리</h4>
              <Link to="/port">Stephen Curry</Link>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/port06.png" alt="포트폴리오6" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/port/portMember06.svg" alt="멤버6" />
            </span>
            <div>
              <h4>크피스 폴</h4>
              <Link to="/port">Chris Paul</Link>
            </div>
          </div>
        </div> -->
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      texts: [
        {
          portImg: "./assets/images/port/port01.png",
          iconImg: "./assets/images/port/portMember01.svg",
          title: "마이클 조던",
          desc: "Michael Jordan",
        },
        {
          portImg: "./assets/images/port/port02.png",
          iconImg: "./assets/images/port/portMember02.svg",
          title: "르브론 제임스",
          desc: "Lebron James",
        },
        {
          portImg: "./assets/images/port/port03.png",
          iconImg: "./assets/images/port/portMember03.svg",
          title: "코비 브라이언트",
          desc: "Kobe Bryant",
        },
        {
          portImg: "./assets/images/port/port04.png",
          iconImg: "./assets/images/port/portMember04.svg",
          title: "케빈 듀란트",
          desc: "Kevin Durant",
        },
        {
          portImg: "./assets/images/port/port05.png",
          iconImg: "./assets/images/port/portMember05.svg",
          title: "스테판 커리",
          desc: "Stephen Curry",
        },
        {
          portImg: "./assets/images/port/port06.png",
          iconImg: "./assets/images/port/portMember06.svg",
          title: "크리스 폴",
          desc: "Chris Paul",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
// port__wrap
.port__inner {
  .port__btn {
    margin-bottom: 30px;
    button {
      width: 8%;
      background-color: #5f81d8;
      border: 1px solid #5f81d8;
      border-radius: 50px;
      margin: 10px;
      padding: 5px;
    }
    button.active {
      background-color: #3969e4;
      border: 1px solid #3969e4;
    }
  }
  .port__cont {
    @include flex-between;
    flex-wrap: wrap;
    .port {
      width: 32%;
      .port__header {
        margin-bottom: 10px;
        img {
          width: 100%;
        }
      }
      .port__body {
        display: flex;
        align-items: center;
        justify-content: space-between;
        span {
          border-radius: 50px;
          img {
            width: 50px;
            height: 50px;
          }
        }
        > div {
          margin-top: 10px;
          width: 80%;
          text-align: left;
          h4 {
            margin-bottom: 5px;
            font-size: 24px;
          }
          a {
            color: #a0a0a0;
          }
          a:hover {
            text-decoration: underline;
            text-underline-position: under;
          }
        }
      }
      &:nth-child(1),
      &:nth-child(2),
      &:nth-child(3) {
        margin-bottom: 50px;
      }
      &:nth-child(1) .port__body span {
        background-color: #c5a8a8;
      }
      &:nth-child(2) .port__body span {
        background-color: #c5c5a8;
      }
      &:nth-child(3) .port__body span {
        background-color: #a8c5ad;
      }
      &:nth-child(4) .port__body span {
        background-color: #a8bac5;
      }
      &:nth-child(5) .port__body span {
        background-color: #a8acc5;
      }
      &:nth-child(6) .port__body span {
        background-color: #bca8c5;
      }
    }
  }
}
</style>
