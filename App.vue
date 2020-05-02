<template>
  <div>
    <Header />
    <UserList />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import UserList from "./components/UserList.vue";

export default {
  name: "componentApp",
  components: {
    Header,
    UserList
  }
};
</script>