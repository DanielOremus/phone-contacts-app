<template>
  <div>
    <div>
      <img :src="photoSrc" alt="" />
    </div>
    <div>
      <label>
        Name
        <input type="text" v-model="user.name" />
      </label>
    </div>
    <div>
      <label>
        Second name
        <input type="text" v-model="user.secondName" />
      </label>
    </div>
    <div>
      <label>
        Address
        <input type="text" v-model="user.address" />
      </label>
    </div>
    <div>
      <label>
        Email
        <input type="email" v-model="user.email" />
      </label>
    </div>
    <div>
      <button @click="onSave">{{ saveBtnTitle }}</button>
      <button @click="onDelete">{{ delBtnTitle }}</button>
    </div>
  </div>
</template>

<script>
import store from "@/store";
export default {
  name: "EditUserForm",

  data() {
    return {
      user: {},
    };
  },

  computed: {
    photoSrc() {
      return this.user.photoSrc ?? require("@/assets/images/user.png");
    },
    currentUserId() {
      return this.$route.params.id;
    },
    saveBtnTitle() {
      return this.currentUserId ? "Save" : "Add";
    },
    delBtnTitle() {
      return this.currentUserId ? "Delete" : "Cancel";
    },
  },

  methods: {
    onSave() {
      if (this.currentUserId) store.updateUser(this.user);
      else store.addUser(this.user);
      this.$router.push({ name: "home" });
    },
    onDelete() {
      if (this.currentUserId) store.deleteUser(this.currentUserId);
      this.$router.push({ name: "home" });
    },
  },
};
</script>

<style lang="scss" scoped>
</style>