<template>
  <div>
    <label>
      ユーザー名変更フォーム：
      <!-- ここでpropsを渡すのではなく、dataを渡す -->
      <input v-model="userNameData" />
    </label>
    <button @click="changeName">名前変更</button>
  </div>
</template>
<script>
export default {
  props: {
    userName: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      userNameData: this.userName
    };
  },
  methods: {
    changeName() {
      // this.$emitで親コンポーネントに値を渡す。第一引数には親コンポーネントで定義したv-onのイベント名を設定する。第二引数には、親に渡す値を設定する。
      this.$emit("update:user-name", this.userNameData);
    }
  }
};
</script>
<style>
input {
  border: 1px solid #ee0000;
}
</style>