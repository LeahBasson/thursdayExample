<template>
  <div class="container">
    <div class="row">
      <UserDetail firstName="Leah" lastName="Basson"/>
      <UserDetail firstName="Jamin" lastName="Langeveldt"/>
    </div>

    <div class="row">
      <h2>App component</h2>
    </div>

    <div class="row gap-2">

     <Card v-for="(friend, index) in friends" :key="index"> 
      <template #cardHeader>
        <img :src="friend.profile" :alt="friend.firstName" loading="eager" class="img-fluid"/>
      </template>
      <template #cardBody>
        <p>{{ friend.firstName }} {{ friend.lastName }}</p>
      </template>
     </Card>

    </div>

  </div>
</template>

<script>
import UserDetail from '@/components/UserDetail.vue';
import Card from '@/components/Card.vue';

export default {
  name: 'App',
  components: {
    UserDetail,
    Card
  },
  data() {
    return {
      friends: [
        {
          firstName: 'Jamin',
          lastName: 'Langeveldt',
          profile: "https://leahbasson.github.io/MyImages/images/Jamin.png"
        },
        {
          firstName: 'Katelin',
          lastName: 'Bock',
          profile: "https://leahbasson.github.io/MyImages/images/Katelin.png"
        },
        {
          firstName: 'Joel',
          lastName: 'Mukanya',
          profile: "https://leahbasson.github.io/MyImages/images/joel5.png"
        },
        {
          firstName: 'Tarryn',
          lastName: 'Arendse',
          profile: "https://leahbasson.github.io/MyImages/images/Tarryn.png"
        },
        {
          firstName: 'Zoë',
          lastName: 'Saaiers',
          profile: "https://leahbasson.github.io/MyImages/images/Zoe.png"
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2C3E50;
  margin-top: 60px;
}
</style>


