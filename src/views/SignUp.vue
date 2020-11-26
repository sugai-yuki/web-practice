<template>
  <div>
    <HeaderAuth />
    <div class="card">
      <p>新規登録</p>
      <div class="form">
        <input placeholder="ユーザーネーム" type="text" v-model="name" />
        <input placeholder="プロフィール" type="text" v-model="profile"/>
        <input placeholder="メールアドレス" type="email" v-model="email" />
        <input placeholder="パスワード" type="password" v-model="password" />
        <button @click="auth">新規登録</button>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
import axios from "axios";
export default {
  data(){
    return{
      name: "",
      profile: "",
      email: "",
      password: "",
    };
  },
  components: {
    HeaderAuth
  },
  methods: {
    auth(){
      axios
        .post("https://cryptic-hollows-00296.herokuapp.com/api/register", {
          name: this.name,
          profile: this.profile,
          email: this.email,
          password: this.password,
        })
        .then(response => {
          console.log(response);
          this.$router.replace("/");
        })
        .catch(error => {
          alert(error);
        });
    }
  }
};
</script>
