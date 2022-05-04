<template>
  <div>
    <user-card v-for="user in usersList" :key="user.id" />
  </div>
</template>

<script>
import UserCard from "./UserCard";
import store from "@/store";

export default {
  name: "UsersList",

  components: {
    UserCard,
  },
};
</script>

<style lang="scss" scoped>
</style>