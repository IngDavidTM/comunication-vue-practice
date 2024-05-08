<template>
  <h1>Vue Comunication Practice</h1>
  <user-data @user-submitted="addUser"></user-data>
  <active-user v-for="user in users" :key="user.id" :name="user.name" :age="user.age"></active-user>
</template>

<script>
  export default {
    data() {
      return {
        users: []
      }
    },
    methods: {
      addUser(user) {
        this.users.push(user);
      }
    }
  }
</script>