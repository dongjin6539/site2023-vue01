<template>
  <div className="movie__search">
    <h2 className="blind">검색하기</h2>
    <input
      ref="{inputRef}"
      type="search"
      onKeyPress="{onKeyPress}"
      placeholder="영화 검색하기"
    />
    <button type="submit">검색</button>
  </div>
</template>
