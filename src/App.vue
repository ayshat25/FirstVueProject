<template>
  <input type="text" v-model="userName" placeholder="Имя">
  <input type="password" v-model="userPass" placeholder="Пароль">
  <input type="email" v-model="userEmail" placeholder="Email">
  <button @click="sendData()">Отправить</button>
</template>
 
<script>
  export default {
    data(){
      return{
        users: [],
        userName: '',
        userPass: '',
        userEmail: ''
      }
    },
    methods: {
      sendData(){
        this.users.push({
          name: this.userName,
          pass: this.userPass,
          email: this.userEmail
        })
      }
    }
  }
</script>
 
<style scoped>

</style>