<template>
  <div>
    <button @click="clickLog">クリック</button>
    <button @mouseenter="hoverLog">hover</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "hello"
    };
  },
  methods: {
    clickLog(event) {
      console.log(event);
      console.log(event.target);
      console.log(this.message);
    },
    hoverLog(event) {
      console.log(event);
      console.log(event.target);
    }
  }
};
</script>

<style>
</style>