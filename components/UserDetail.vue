<template>
  <div>
    <h2>選択中のユーザー</h2>
    <p>{{ user.name }}</p>
  </div>
</template>
<script>
export default {
  name: "UserDetail",
  // 親コンポーネントから受け取る型を定義
  // propsそのものを書き換えるのはNGだが、propsのプロパティを直接書き換えることはできる
  props: {
    user: {
      type: Object
    }
  }
};
</script>