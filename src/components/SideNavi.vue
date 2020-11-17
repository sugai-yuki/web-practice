<template>
  <div>
    <div class="left-padding">
      <img class="logo" src="../assets/logo.png" />
      <div class="flex icon-field" @click="$router.push('/home')">
        <img class="icon" src="../assets/home.png" />
        <p>ホーム</p>
      </div>
      <div class="flex icon-field" @click="$router.push('/profile')">
        <img class="icon" src="../assets/profile.png" />
        <p>プロフィール</p>
      </div>
      <div class="flex icon-field" @click="$store.dispatch('logout')">
        <img class="icon" src="../assets/logout.png" />
        <p>ログアウト</p>
      </div>
    </div>
    <hr />
    <ShareMessage />
  </div>
</template>

<script>
import ShareMessage from "../components/ShareMessage";
export default {
  components: {
    ShareMessage
  }
};
</script>

<style scoped>
.left-padding {
  margin: 20px;
}
.logo {
  width: 100px;
  cursor: pointer;
}
.icon-field {
  margin-top: 15px;
  cursor: pointer;
}
.icon-field p {
  font-size: 16px;
  padding-left: 15px;
}
</style>