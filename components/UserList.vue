<template>
  <div>
    <h2>ユーザーリスト</h2>
    <ul>
      <li v-for="user in users" :key="user.id" @click="selectedUser = user">{{ user.name }}</li>
    </ul>
    <UserDetail :user="selectedUser" />
  </div>
</template>
<script>
import UserDetail from "./UserDetail.vue";
export default {
  name: "UserList",
  components: {
    UserDetail
  },
  data() {
    return {
      users: [
        { id: 1, name: "ユーザー1" },
        { id: 2, name: "ユーザー2" },
        { id: 3, name: "ユーザー3" },
        { id: 4, name: "ユーザー4" },
        { id: 5, name: "ユーザー5" }
      ],
      selectedUser: {}
    };
  }
};
</script>