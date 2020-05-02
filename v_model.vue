<template>
  <div>
    <div>
      <label>
        <span>名前：</span>
        <input v-model="name" />
      </label>
    </div>
    <div>
      <label>
        <span>email：</span>
        <input v-model="email" />
      </label>
    </div>
    <div>
      <label>
        <span>問い合わせ</span>
        <textarea rows="10" v-model="text"></textarea>
      </label>
    </div>
    <button @click="submit">送信</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "山田",
      email: "hoge@yamada.com",
      text: "hogehoge"
    };
  },
  methods: {
    submit() {
      const inquiry = `
      お問い合わせがありました。

      名前：${this.name}
      メールアドレス：${this.email}
      問い合わせ内容：${this.text}
      `;

      alert(inquiry);
    }
  }
};
</script>

<style>
</style>template>