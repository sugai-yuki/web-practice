<template>
 <div>
   <HeaderAuth />
   <div class="card">
     <p>ログイン</p>
     <div class="form">
       <input placeholder="メールアドレス" type="email" />
       <input placeholder="パスワード" type="password" />
       <button>ログイン</button>
     </div>
   </div>
 </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
export default {
 components: {
   HeaderAuth
 }
};
</script>