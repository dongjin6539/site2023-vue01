<template>
  <section id="introSection" class="intro__wrap gmarket5 section">
    <h3 class="blind">농구 튜툐리얼 소개</h3>
    <div class="intro__inner container">
      <div class="intro__title">
        <span>basketball</span>
        <h3 v-html="title"></h3>
        <p v-html="desc"></p>
        <img src="@/assets/images/intro/intro.png" alt="소개" />
      </div>
      <div class="intro__desc2">
        <div v-for="(text, index) in texts" :key="index">
          <h4 :class="'icon-bg' + (index + 1)">{{ text.title }}</h4>
          <p>
            {{ text.desc }}
          </p>
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
      title: "농구 입문<br />전문과정",
      desc: "농구를 시작하는 전문 과정입니다.<br />처음 시작하는 분들에게 필요합니다.",
      texts: [
        {
          title: "기본 기술",
          desc: "농구를 잘하기 위해서는 기본적인 농구 기술을 익히는 것이 중요합니다. 드리블, 패스, 샷, 리바운드 등의 기본 기술들을 연습하고 개선해야 합니다. 또한 바른 자세와 테크닉을 익히는 것도 중요합니다.",
        },
        {
          title: "체력과 유연성",
          desc: "농구는 높은 수준의 체력과 유연성을 요구합니다. 빠른 움직임, 높은 점프, 긴 시간동안의 활동 등을 위해 근력과 유연성을 향상시키는 훈련을 해야 합니다. 스피드, 스태미너, 근력, 유연성을 모두 개발하도록 훈련 프로그램을 구성하는 것이 좋습니다.",
        },
        {
          title: "게임 이해력",
          desc: "농구는 전략과 팀워크가 중요한 경기입니다. 게임 상황을 잘 이해하고 상황에 맞는 판단과 의사 소통을 할 수 있어야 합니다. 다양한 게임 상황을 경험하고 분석하며 팀원들과의 협업을 통해 게임 이해력을 향상시킬 수 있습니다.",
        },
        {
          title: "의지와 열정",
          desc: "농구는 경기 중간에 발생하는 실패와 어려움에 대처하는 능력을 요구합니다. 의지와 열정을 가지고 노력하며 꾸준한 훈련과 연습을 통해 개인 기술을 향상시켜야 합니다. 열심히 노력하고 계속해서 도전하는 자세가 중요합니다.",
        },
        {
          title: "실전적인 경험",
          desc: "지역 농구 팀이나 학교의 농구 동아리에 가입하여 실전 경험을 쌓아보세요. 경기에서 팀원들과 함께 협력하고 전략을 구사하는 능력을 키울 수 있습니다. 친구들과 함께 농구를 즐길 수 있는 기회를 찾아보세요. 농구는 다수가 참여하는 운동이므로, 친구들과 함께 하면 더욱 재미있게 배울 수 있습니다.",
        },
        {
          title: "전문 교육",
          desc: "전문적인 농구 교육 프로그램을 찾아보세요. 지역 체육관이나 농구 클럽, 학교에서 제공하는 교육 과정을 찾아보세요. 전문 강사들로부터 기본 기술 및 전략을 배울 수 있습니다. 온라인 자료를 활용하세요. 유튜브나 온라인 농구 교육 사이트에서도 다양한 농구 기술과 전략에 대한 동영상 자료를 찾아볼 수 있습니다.",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
// intro__wrap
.intro__inner {
  display: flex;
  justify-content: space-between;
}
.intro__title {
  width: 33%;
  span {
    font-size: 14px;
    padding: 4px 30px 2px;
    background-color: #ff3344;
    border-radius: 40px;
    color: #fff;
    text-transform: uppercase;
    margin-bottom: 10px;
    display: inline-block;
  }
  h3 {
    font-size: 50px;
    line-height: 1.2;
    margin-bottom: 26px;
    margin-bottom: 30px;
  }
  p {
    font-size: 18px;
    line-height: 1.5;
    font-weight: 500;
    margin-bottom: 100px;
  }
  img {
    width: 70%;
  }
}
.intro__desc {
  width: 67%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  position: relative;
  > div {
    width: 48%;
    margin-bottom: 40px;
    h4 {
      font-size: 24px;
      margin-bottom: 20px;
    }
    &:nth-child(3) {
      margin-bottom: 0;
    }
    &:nth-child(4) {
      margin-bottom: 0;
    }
  }
}
.intro__desc2 {
  width: 67%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  position: relative;
  > div {
    width: 48%;
    margin-bottom: 40px;
    h4 {
      font-size: 24px;
      margin-bottom: 20px;
    }
    &:nth-child(5) {
      margin-bottom: 0;
    }
    &:nth-child(6) {
      margin-bottom: 0;
    }
  }
}
</style>
