<template>
  <div>
    <!-- <p @input="changeUserName"></p> -->
    <p>{{ userName }}</p>
    <!-- :user-name="userName"は子のコンポーネントに値をセットする -->
    <!-- @update:user-nameで子のコンポーネントからイベント発火を受け取る -->
    <!-- イベント発火したらuserName = $eventでuserNameの値が書き換わる -->
    <!-- $eventにはthis.$emit("update:user-name", this.userNameData);の第二引数の値が入っている -->
    <UserForm :user-name.sync="userName" />
  </div>
</template>
<script>
import UserForm from "./UserForm.vue";
export default {
  components: {
    UserForm
  },
  data() {
    return {
      userName: "masanari hori"
    };
  }
};
</script>