<template>
  <div :title="message">
    {{ message }}
    <p>{{ sum | numberWithDelimiter }}円</p>
    <button :disabled="isButtonDisadled" @click="log">{{ buttonLabel }}</button>
    <button :disabled="isButtonDisadled">{{ buttonLabel }}</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "sample",
      sum: undefined,
      isButtonDisadled: false
    };
  },
  filters: {
    // valueを受け取って処理をする
    numberWithDelimiter(value) {
      if (!value) {
        return "0";
      }
      return value.toString().replace(/(\d)(?=(\d{3})+$)/g, "$1,");
    }
  },
  computed: {
    // メソッドはデータが変更された時のみ呼び出されて、それ以外の場合はキャッシュが返される
    buttonLabel() {
      console.log("isButtonDisadled, called");
      return this.isButtonDisadled ? "無効" : "有効";
    },
    // 関連するデータが変更されない限り、一度実行して、キャッシュされた値を返すので、再実行されない
    // あくまでcomputedプロパティでは、データとして処理を加えた結果を値として提供したい場合に使う
    // このnowメソッドは常に同じ時刻を返し続ける
    now() {
      return new Date().toTimeString();
    }
  },
  methods: {
    log() {
      console.log(this.now);
    }
  }
};
</script>

<style>
p {
  margin: 20px;
}
</style>