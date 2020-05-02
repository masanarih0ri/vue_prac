<template>
  <div>
    <div>
      <label for>
        <input type="checkbox" v-model="isChecked" />予約する
      </label>
    </div>
    <!-- v-showはdisplay: none;で要素を消している -->
    <!-- <div v-show="isChecked">
      予約日:
      <input type="date" name id />
    </div>-->
    <!-- v-showはdisplay: none;で要素を消している -->
    <!-- v-ifはDOM要素の削除、追加を行う（こっちの方がレンダリングコストが高い） -->
    <div v-if="isChecked">
      予約日:
      <input type="date" name id />
    </div>
    <div class="contents">
      <div v-if="contentsMessage">{{ contentsMessage }}</div>
      <div v-else-if="contentsMessage === ''">メッセージが空です</div>
      <div v-else>メッセージがありません</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isChecked: false,
      contentsMessage: "message"
    };
  }
};
</script>

<style>
</style>