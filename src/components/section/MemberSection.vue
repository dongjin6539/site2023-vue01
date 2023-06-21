<template>
  <section id="memberSection" class="member__wrap gmarket5 section center">
    <h3>레전드 선수</h3>
    <p>레전드 선수를 소개합니다.</p>
    <div class="member__inner container">
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member01.png" alt="멤버1" />
        </figure>
        <div class="member__body">
          <h4>마이클 조던</h4>
          <router-link to="/">경력 보기</router-link>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member02.png" alt="멤버1" />
        </figure>
        <div class="member__body">
          <h4>코비 브라이언트</h4>
          <router-link to="/">경력 보기</router-link>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/member03.png" alt="멤버1" />
        </figure>
        <div class="member__body">
          <h4>르브론 제임스</h4>
          <router-link to="/">경력 보기</router-link>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
// member__wrap
.member__inner {
  @include flex-between;
  // display: flex;
  // justify-content: space-between;
  .member {
    width: 32%;
    .member__header {
      margin-bottom: 18px;
      img {
        width: 100%;
        height: 600px;
      }
    }
    .member__body {
      margin-top: -90px;
      padding: 10px;
      background: #000;
      color: #fff;
      z-index: 100;
      position: relative;
      h4 {
        font-size: 22px;
      }
      a {
        color: #fff;
        text-decoration: underline;
        text-underline-position: under;
      }
    }
    &:nth-child(1) .member__body {
      background: #fd000096;
    }
    &:nth-child(2) .member__body {
      background: #9900ff8a;
    }
    &:nth-child(3) .member__body {
      background: #fffb0073;
    }
  }
}
</style>
