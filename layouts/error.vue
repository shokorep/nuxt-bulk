<template>
  <div class="container">
    <h1>{{ error.statusCode }}</h1>
    <p v-if="error.statusCode === 404">
      ページが見つかりません
    </p>
    <p v-else>
      エラーが発生しました
    </p>
  </div>
</template>

<script>
import ArticleBody from '~/components/common/ArticleBody';
export default {
  components: {
      ArticleBody
    },
  props: {
    error: {
      type: Object,
      default: null
    }
  }
}
</script>

<style scoped lang="scss">
  @import "~assets/scss/variables";

  .error {
    h2 {
      display: flex;
      align-items: center;
      margin: 50px 0 30px;
      font-size: 30px;

      &::after {
        content: '';
        display: block;
        flex: 1;
        height: 1px;
        margin-left: 10px;
        background-color: $color-black;
      }
    }
  }

  
</style>