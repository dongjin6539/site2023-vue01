<template>
  <div class="youtube__search">
    <h2 class="blind">검색하기</h2>
    <input
      ref="inputRef"
      type="search"
      v-model="searchTerm"
      @keypress="onKeyPress"
      placeholder="유튜브 검색하기"
    />
    <button type="submit" @click="onClick">검색</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchTerm: "", // 검색어를 저장하는 데이터 속성
    };
  },
  methods: {
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
    handleSearch() {
      const value = this.searchTerm; // 검색어를 데이터 속성에서 가져옴
      this.$emit("search", value);
    },
  },
};
</script>
