<template>
  <div className="unsplash__cont container">
    <ul>
      <li v-for="(unsplash, index) in unsplashs" :key="index">
        <a :href="`http://unsplash.com/photos/${unsplash.id}`" target="_blank">
          <img :src="unsplash.urls.regular" :alt="unsplash.alt_description" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    unsplashs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.unsplash__cont {
  ul {
    column-count: 4;
    li {
      margin-bottom: 20px;
    }
  }
}
</style>
