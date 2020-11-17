<template>
  <div class="flex">
    <div class="left">
      <SideNavi />
    </div>
    <div class="right">
      <div class="title">
        <p>プロフィール</p>
      </div>
      <div class="profile">
        <div class="flex between">
          <p class="profile-name">{{name}}</p>
          <div @click="edit">
            <button>変更する</button>
          </div>
        </div>
        <p class="text" v-if="active">{{profile}}</p>
        <input type="text" v-model="profile" v-else />
      </div>
      <Message />
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi";
import Message from "../components/Message";
export default {
  data() {
    return {
      active: true,
      name: "太郎",
      profile: "私は太郎です"
    };
  },
  components: {
    SideNavi,
    Message
  }
};
</script>

<style scoped>
.profile {
  padding: 20px;
  border-bottom: solid 1px white;
  border-left: 1px solid white;
}
.profile-name {
  font-size: 24px;
}
</style>