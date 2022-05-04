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
  },
};
</script>

<style lang="scss" scoped>
</style>