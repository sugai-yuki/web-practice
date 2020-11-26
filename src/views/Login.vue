<template>
 <div>
   <HeaderAuth />
   <div class="card">
     <p>ログイン</p>
     <div class="form">
       <input placeholder="メールアドレス" type="email" v-model="email" />
       <input placeholder="パスワード" type="password" v-model="password" />
       <button @click="auth">ログイン</button>
     </div>
   </div>
 </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
export default {
  data(){
    return{
      email: "",
      password: "",
    };
  },
 components: {
   HeaderAuth
 },
 methods: {
   auth(){
     this.$store.dispatch("login", {
       email: this.email,
       password: this.password,
     });
   }
 }
};
</script>