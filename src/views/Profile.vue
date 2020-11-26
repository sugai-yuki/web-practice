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
import axios from "axios";
export default {
  data() {
    return {
      active: true,
      name: this.$store.state.user.name,
      profile: this.$store.state.user.profile,
    };
  },
  mthods: {
    edit() {
      if (!this.active) {
        axios
         .put("https://cryptic-hollows-00296.herokuapp.com/api/user", {
           email: this.$store.state.user.email,
           profile: this.profile,
         })
         .then((response) => {
           this.$store.dispatch("changeUserData", {
             profile: this.profile,
           });
           console.log(response);
         });
      }
      this.active = !this,active;
    },
  },
  components: {
    SideNavi,
    Message
  },
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