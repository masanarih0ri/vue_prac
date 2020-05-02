<template>
  <div>
    <Layout>
      <!-- slot属性の名前がheaderとすると、Layoutコンポーネントにあるslotタグのname属性がheaderの箇所に、「Header」というテキストがセットされている -->
      <template slot="header">Header</template>
      Main Contents
      <span slot="footer">footer</span>
    </Layout>
  </div>
</template>

<script>
import Layout from "./components/Layout.vue";

export default {
  components: {
    Layout
  }
};
</script>