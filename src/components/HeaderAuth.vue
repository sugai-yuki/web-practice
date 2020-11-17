<template>
 <div class="header flex between">
   <div class="header_left">
     <img class="logo" src="../assets/logo.png"/>
   </div>
   <div class="header_right flex between">
     <p @click="$router.push('/signup')">新規登録</p>
     <p @click="$router.push('/')">ログイン</p>
   </div>
 </div>
</template>

<style scoped>
.header_right {
 align-items: center;
}
.header_right p {
 margin-right: 20px;
 cursor: pointer;
}
.header {
 margin: 20px;
}
.logo {
 width: 150px;
 cursor: pointer;
}
</style>