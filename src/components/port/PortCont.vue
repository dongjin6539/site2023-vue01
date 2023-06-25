<template>
  <section id="portSection" class="port__wrap gmarket5 section center">
    <h3>농구 유명인</h3>
    <p>각 리그 별 농구 유명인입니다.</p>
    <div class="port__inner container">
      <div class="port__btn">
        <button
          :class="{ active: activeButton === 'NBA' }"
          @click="activeButton = 'NBA'"
        >
          NBA
        </button>
        <button
          :class="{ active: activeButton === 'WNBA' }"
          @click="activeButton = 'WNBA'"
        >
          WNBA
        </button>
        <button
          :class="{ active: activeButton === 'KBL' }"
          @click="activeButton = 'KBL'"
        >
          KBL
        </button>
        <button
          :class="{ active: activeButton === 'WKBL' }"
          @click="activeButton = 'WKBL'"
        >
          WKBL
        </button>
      </div>
      <div class="port__cont2">
        <div class="port" v-for="(text, index) in filteredTexts" :key="index">
          <a :href="text.link" target="_blank">
            <figure class="port__header">
              <img :src="text.portImg" :alt="text.alt" />
            </figure>
            <div class="port__body">
              <span>
                <img :src="text.iconImg" :alt="text.alt" />
              </span>
              <div>
                <h4>{{ text.title }}</h4>
                <p>{{ text.desc }}</p>
              </div>
            </div>
          </a>
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
  data: function () {
    return {
      activeButton: "NBA", // 초기에 NBA 버튼이 활성화되도록 설정
      texts: [
        {
          portImg: "./assets/images/port/port01.png",
          iconImg: "./assets/images/port/portMember01.svg",
          title: "마이클 조던",
          desc: "Michael Jordan",
          link: "https://namu.wiki/w/%EB%A7%88%EC%9D%B4%ED%81%B4%20%EC%A1%B0%EB%8D%98",
        },
        {
          portImg: "./assets/images/port/port02.png",
          iconImg: "./assets/images/port/portMember02.svg",
          title: "르브론 제임스",
          desc: "Lebron James",
          link: "https://namu.wiki/w/%EB%A5%B4%EB%B8%8C%EB%A1%A0%20%EC%A0%9C%EC%9E%84%EC%8A%A4",
        },
        {
          portImg: "./assets/images/port/port03.png",
          iconImg: "./assets/images/port/portMember03.svg",
          title: "코비 브라이언트",
          desc: "Kobe Bryant",
          link: "https://namu.wiki/w/%EC%BD%94%EB%B9%84%20%EB%B8%8C%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8",
        },
        {
          portImg: "./assets/images/port/port04.png",
          iconImg: "./assets/images/port/portMember04.svg",
          title: "케빈 듀란트",
          desc: "Kevin Durant",
          link: "https://namu.wiki/w/%EC%BC%80%EB%B9%88%20%EB%93%80%EB%9E%80%ED%8A%B8",
        },
        {
          portImg: "./assets/images/port/port05.png",
          iconImg: "./assets/images/port/portMember05.svg",
          title: "스테판 커리",
          desc: "Stephen Curry",
          link: "https://namu.wiki/w/%EC%8A%A4%ED%85%8C%ED%8C%90%20%EC%BB%A4%EB%A6%AC",
        },
        {
          portImg: "./assets/images/port/port06.png",
          iconImg: "./assets/images/port/portMember06.svg",
          title: "크리스 폴",
          desc: "Chris Paul",
          link: "https://namu.wiki/w/%ED%81%AC%EB%A6%AC%EC%8A%A4%20%ED%8F%B4",
        },
        {
          portImg: "./assets/images/port/port07.png",
          iconImg: "./assets/images/port/portMember07.svg",
          title: "샤킬 오닐",
          desc: "Shaquille Rashaun O'Neal",
          link: "https://namu.wiki/w/%EC%83%A4%ED%82%AC%20%EC%98%A4%EB%8B%90",
        },
        {
          portImg: "./assets/images/port/port08.png",
          iconImg: "./assets/images/port/portMember08.svg",
          title: "니콜라 요키치",
          desc: "Nikola Jokić",
          link: "https://namu.wiki/w/%EB%8B%88%EC%BD%9C%EB%9D%BC%20%EC%9A%94%ED%82%A4%EC%B9%98",
        },
      ],
      texts2: [
        {
          portImg: "./assets/images/port/port2_01.png",
          iconImg: "./assets/images/port/portMember2_01.svg",
          title: "로렌 잭슨",
          desc: "Lauren Jackson",
          link: "https://namu.wiki/w/%EB%A1%9C%EB%A0%8C%20%EC%9E%AD%EC%8A%A8",
        },
        {
          portImg: "./assets/images/port/port2_02.png",
          iconImg: "./assets/images/port/portMember2_02.svg",
          title: "다이애나 터라시",
          desc: "Diana Taurasi",
          link: "https://en.wikipedia.org/wiki/Diana_Taurasi",
        },
        {
          portImg: "./assets/images/port/port2_03.png",
          iconImg: "./assets/images/port/portMember2_03.svg",
          title: "타미카 캐칭스",
          desc: "Tamika Catchings",
          link: "https://namu.wiki/w/%ED%83%80%EB%AF%B8%EC%B9%B4%20%EC%BA%90%EC%B9%AD",
        },
        {
          portImg: "./assets/images/port/port2_04.png",
          iconImg: "./assets/images/port/portMember2_04.svg",
          title: "마야 무어",
          desc: "Maya Moore",
          link: "https://en.wikipedia.org/wiki/Maya_Moore",
        },
        {
          portImg: "./assets/images/port/port2_05.png",
          iconImg: "./assets/images/port/portMember2_05.svg",
          title: "켄디스 파커",
          desc: "Candace Parker",
          link: "https://en.wikipedia.org/wiki/Candace_Parker",
        },
        {
          portImg: "./assets/images/port/port2_06.png",
          iconImg: "./assets/images/port/portMember2_06.svg",
          title: "리사 디숀 레슬리",
          desc: "Lisa Deshaun Leslie",
          link: "https://en.wikipedia.org/wiki/Lisa_Leslie",
        },
        {
          portImg: "./assets/images/port/port2_07.png",
          iconImg: "./assets/images/port/portMember2_07.svg",
          title: "레베카 함몬",
          desc: "Rebecca Hammon",
          link: "https://ko.wikipedia.org/wiki/%EB%B2%A0%ED%82%A4_%ED%95%B4%EB%A8%BC",
        },
        {
          portImg: "./assets/images/port/port2_08.png",
          iconImg: "./assets/images/port/portMember2_08.svg",
          title: "수 버드",
          desc: "Sue Bird",
          link: "https://en.wikipedia.org/wiki/Sue_Bird",
        },
      ],
      texts3: [
        {
          portImg: "./assets/images/port/port3_01.png",
          iconImg: "./assets/images/port/portMember3_01.svg",
          title: "허재",
          desc: "Hur Jae",
          link: "https://namu.wiki/w/%ED%97%88%EC%9E%AC",
        },
        {
          portImg: "./assets/images/port/port3_02.png",
          iconImg: "./assets/images/port/portMember3_02.svg",
          title: "서장훈",
          desc: "Seo Jang-hoon",
          link: "https://namu.wiki/w/%EC%84%9C%EC%9E%A5%ED%9B%88",
        },
        {
          portImg: "./assets/images/port/port3_03.png",
          iconImg: "./assets/images/port/portMember3_03.svg",
          title: "우지원",
          desc: "Woo Ji-won",
          link: "https://namu.wiki/w/%EC%9A%B0%EC%A7%80%EC%9B%90",
        },
        {
          portImg: "./assets/images/port/port3_04.png",
          iconImg: "./assets/images/port/portMember3_04.svg",
          title: "현주엽",
          desc: "Hyun Ju-yeop",
          link: "https://namu.wiki/w/%ED%98%84%EC%A3%BC%EC%97%BD",
        },
        {
          portImg: "./assets/images/port/port3_05.png",
          iconImg: "./assets/images/port/portMember3_05.svg",
          title: "하승진",
          desc: "Ha Seung-jin",
          link: "https://namu.wiki/w/%ED%95%98%EC%8A%B9%EC%A7%84",
        },
        {
          portImg: "./assets/images/port/port3_06.png",
          iconImg: "./assets/images/port/portMember3_06.svg",
          title: "허웅",
          desc: "Heo Ung",
          link: "https://namu.wiki/w/%ED%97%88%EC%9B%85",
        },
        {
          portImg: "./assets/images/port/port3_07.png",
          iconImg: "./assets/images/port/portMember3_07.svg",
          title: "허훈",
          desc: "Heo Hoon",
          link: "https://namu.wiki/w/%ED%97%88%ED%9B%88",
        },
        {
          portImg: "./assets/images/port/port3_08.png",
          iconImg: "./assets/images/port/portMember3_08.svg",
          title: "김선형",
          desc: "Kim Sun-hyung",
          link: "https://namu.wiki/w/%EA%B9%80%EC%84%A0%ED%98%95",
        },
      ],
      texts4: [
        {
          portImg: "./assets/images/port/port4_01.png",
          iconImg: "./assets/images/port/portMember4_01.svg",
          title: "김단비",
          desc: "Kim Dan-bi",
          link: "https://namu.wiki/w/%EA%B9%80%EB%8B%A8%EB%B9%84(1990)",
        },
        {
          portImg: "./assets/images/port/port4_02.png",
          iconImg: "./assets/images/port/portMember4_02.svg",
          title: "김소니아",
          desc: "Sonia Ursu-Kim",
          link: "https://namu.wiki/w/%EA%B9%80%EC%86%8C%EB%8B%88%EC%95%84",
        },
        {
          portImg: "./assets/images/port/port4_03.png",
          iconImg: "./assets/images/port/portMember4_03.svg",
          title: "강이슬",
          desc: "Kang Lee-seul",
          link: "https://namu.wiki/w/%EA%B0%95%EC%9D%B4%EC%8A%AC",
        },
        {
          portImg: "./assets/images/port/port4_04.png",
          iconImg: "./assets/images/port/portMember4_04.svg",
          title: "박지수",
          desc: "Park Ji-Su",
          link: "https://namu.wiki/w/%EB%B0%95%EC%A7%80%EC%88%98(%EB%86%8D%EA%B5%AC%EC%84%A0%EC%88%98)",
        },
        {
          portImg: "./assets/images/port/port4_05.png",
          iconImg: "./assets/images/port/portMember4_05.svg",
          title: "박지현",
          desc: "Park Ji-hyun",
          link: "https://namu.wiki/w/%EB%B0%95%EC%A7%80%ED%98%84(%EC%97%AC%EC%9E%90%EB%86%8D%EA%B5%AC)?rev=206",
        },
        {
          portImg: "./assets/images/port/port4_06.png",
          iconImg: "./assets/images/port/portMember4_06.svg",
          title: "전주원",
          desc: "Chun Joo-weon",
          link: "https://namu.wiki/w/%EC%A0%84%EC%A3%BC%EC%9B%90",
        },
        {
          portImg: "./assets/images/port/port4_07.png",
          iconImg: "./assets/images/port/portMember4_07.svg",
          title: "김정은",
          desc: "Kim Jung-eun",
          link: "https://namu.wiki/w/%EA%B9%80%EC%A0%95%EC%9D%80(%EB%86%8D%EA%B5%AC%EC%84%A0%EC%88%98)",
        },
        {
          portImg: "./assets/images/port/port4_08.png",
          iconImg: "./assets/images/port/portMember4_08.svg",
          title: "정선민",
          desc: "Jung Sun-min",
          link: "https://namu.wiki/w/%EC%A0%95%EC%84%A0%EB%AF%BC",
        },
      ],
    };
  },
  computed: {
    filteredTexts() {
      if (this.activeButton === "WNBA") {
        return this.texts2; // WNBA 버튼이 활성화되면 texts2를 반환
      } else if (this.activeButton === "KBL") {
        return this.texts3; // WNBA 버튼이 활성화되면 texts3를 반환
      } else if (this.activeButton === "WKBL") {
        return this.texts4; // WNBA 버튼이 활성화되면 texts4를 반환
      } else {
        return this.texts; // 그 외의 경우에는 texts를 반환
      }
    },
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";

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
      color: #fff;
      &:hover {
        background-color: #3969e4;
        border: 1px solid #3969e4;
        color: #fff;
      }
    }
    button.active {
      background-color: #3969e4;
      border: 1px solid #3969e4;
      color: #fff;
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
          p {
            color: #a0a0a0;
          }
        }
      }
      &:nth-child(1),
      &:nth-child(2),
      &:nth-child(3) {
        margin-bottom: 50px;
      }
      &:hover > a > .port__body > div > p {
        text-decoration: underline;
        text-underline-position: under;
      }
    }
  }
  .port__cont2 {
    @include flex-between;
    flex-wrap: wrap;
    .port {
      width: 23%;
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
          p {
            color: #a0a0a0;
          }
        }
      }
      &:nth-child(1),
      &:nth-child(2),
      &:nth-child(3),
      &:nth-child(4) {
        margin-bottom: 50px;
      }
      &:hover > a > .port__body > div > p {
        text-decoration: underline;
        text-underline-position: under;
      }
    }
  }
}
</style>
