<template>
  <div>
    <div v-if="usersList.length">
      <user-card v-for="user in usersList" :key="user.id" />
    </div>
    <div v-else>No data</div>
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

  data() {
    return {
      usersList: [],
    };
  },

  mounted() {
    this.usersList = store.readList();
  },
};
</script>

<style lang="scss" scoped>
</style>