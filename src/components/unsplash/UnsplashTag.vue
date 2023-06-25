<template>
  <div class="unsplash__tag container">
    <div>
      <button
        v-for="(tag, index) in unsplashTags"
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
      unsplashTags: [
        { name: "배경 화면", url: "wallpapers" },
        { name: "3D 랜더링", url: "3d-renders" },
        { name: "자연", url: "nature" },
        { name: "텍스처 및 패턴", url: "textures-patterns" },
        { name: "건축 및 인테리어", url: "architecture-interio" },
        { name: "필름", url: "film" },
        { name: "거리 사진", url: "street-photography" },
        { name: "실험적인", url: "experimental" },
        { name: "동물", url: "animals" },
        { name: "패션 & 뷰티", url: "fashion-beauty" },
        { name: "비즈니스 및 업무", url: "business-work" },
        { name: "식음료", url: "food-drink" },
        { name: "여행", url: "travel" },
        { name: "사람", url: "people" },
        { name: "영성", url: "spirituality" },
        { name: "스포츠", url: "athletics" },
        { name: "건강 및 웰빙", url: "health" },
        { name: "이벤트", url: "current-events" },
        { name: "예술 및 문화", url: "arts-culture" },
      ],
      activeTag: "",
    };
  },
  methods: {
    btnClick(tagName) {
      const clickedTag = this.unsplashTags.find((tag) => tag.name === tagName);
      if (clickedTag) {
        this.activeTag = clickedTag.name;
        this.$emit("search", clickedTag.url);
      }
    },
  },
};
</script>
