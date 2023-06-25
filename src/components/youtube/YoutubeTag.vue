<template>
  <div class="youtube__tag">
    <div>
      <button
        v-for="(tag, index) in youtubeTags"
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
      youtubeTags: [
        { name: "nba" },
        { name: "kbl" },
        { name: "sports" },
        { name: "baseball" },
        { name: "soccor" },
        { name: "basketball" },
      ],
      activeTag: "",
    };
  },
  methods: {
    btnClick(tagName) {
      this.activeTag = tagName;
      this.$emit("search", tagName);
    },
  },
};
</script>

<style lang="scss">
.youtube__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;
    button {
      border: 1px solid #00c183;
      padding: 10px 20px;
      margin: 0 10px;
      color: #00c183;
      background-color: #fff;
      &:hover {
        background-color: #00c183;
        color: #fff;
      }
    }
    button.active {
      background-color: #00c183; /* 선택된 태그의 배경색 */
      color: #ffffff; /* 선택된 태그의 텍스트 색상 */
    }
  }
}
</style>
