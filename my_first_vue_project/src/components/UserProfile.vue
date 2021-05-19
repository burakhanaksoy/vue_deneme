<template>
  <div class="userProfile">
    <div id="isAdmin" v-if="user.isAdmin">Admin</div>
    <div id="normalUser" v-else>Member</div>
    <div id="user-name">@{{ user.username }} - {{ fullName }}</div>
    <div id="followers">
      Followers: <strong>{{ followers }}</strong>
    </div>
    <button id="follower-increment" v-on:click="followUser">Follow!</button>
  </div>
</template>

<script>
export default {
  name: "UserProfile",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "buraktheMan",
        firstName: "Burakhan",
        lastName: "Aksoy",
        email: "burakhan@burakhan.com",
        isAdmin: true,
      },
    };
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },
  mounted() {
    this.followUser();
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.username} has a new follower!`);
      }
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

.userProfile {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: rgb(201, 201, 201);
  border-radius: 40px;
  border: 1px solid;
  margin-right: 2rem;
  max-height: 325px;
}
#follower-increment {
  margin-top: 1rem;
  margin-bottom: 1rem;
  font-size: 20px;
}
#followers {
  display: flex;
  flex-direction: column;
}
#followers strong {
  font-size: 100px;
}
#isAdmin,
#normalUser {
  background: rgb(255, 238, 0);
  min-height: 73px;
  min-width: 73px;
  border-radius: 100%;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  margin: auto;
}
#normalUser {
  background: rgb(252, 147, 252);
}
#tweets {
  float: right;
  list-style: none;
}
</style>