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
      <button>{{ saveBtnTitle }}</button>
    </div>
  </div>
</template>

<script>
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
  },
};
</script>

<style lang="scss" scoped>
</style>