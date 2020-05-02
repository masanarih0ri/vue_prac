<template>
  <div>{{ message }}</div>
</template>
<script>
export default {
  data() {
    return {
      message: "サンプル",
      interval_id: null
    };
  },
  beforeCreate() {
    console.log("vueインスタンス作成前");
  },
  created() {
    console.log("vueインスタンス作成後");
    // this.message = "インスタンス作成後";
    // インスタンスの作成とともに定期実行する処理を書くことができる
    let interval = 0;
    setInterval(() => {
      console.log(`${interval++}秒経過`);
    }, 1000);
  },
  beforeMount() {
    console.log("マウント前");
  },
  mounted() {
    console.log("マウント後");
  },
  beforeUpdate() {
    console.log("再描画前");
  },
  updated() {
    console.log("再描画後");
  },
  beforeDestroy() {
    console.log("vueインスタンス削除前");
    // clearInterval(this.intervalId);
  },
  destroyed() {
    console.log("vueインスタンス削除後");
  }
};
</script>
<style>
</style>