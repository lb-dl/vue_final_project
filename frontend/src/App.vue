<template>
  <h1>{{greeting}}</h1>
  <li v-for="(user, index) in users" :key="index">
    <ul>{{ user.id }}. {{user.firstname}} {{user.lastname}} - {{user.email}} {{user.created_at}}</ul>
  </li>

</template>

<script>
export default {

  data: function(){
    return {
      greeting: 'Test Vue!',
      users: []
    }
  },
  created: async function(){
    const response = await fetch("http://localhost:8000/api/v1/users");
    this.users = await response.json();
  }
}
</script>

<style scoped>

</style>
