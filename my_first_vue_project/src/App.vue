<template>
  <nav>
    <div class="nav-bar">
      <div class="text-field-site">Hello</div>
      <div class="text-field-user">Burakhan</div>
    </div>
  </nav>
  <div id="mainPage">
    <UserProfile />
    <Tweets />
  </div>
</template>

<script>
import UserProfile from "./components/UserProfile";
import Tweets from "./components/Tweets";
// import SubmitTweet from "./components/SubmitTweet";

export default {
  name: "App",
  components: { UserProfile, Tweets },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 20px;
  justify-content: center;
  display: flex;
  align-items: center;
  flex-direction: column;
}
#mainPage {
  display: flex;
  flex-direction: row;
  margin: 1rem;
}
#submit-btn {
  margin-top: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100rem;
}

.nav-bar {
  margin-bottom: 2rem;
  background-color: rgb(53, 89, 121);
  width: 90rem;
  color: aliceblue;
  height: 3rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  font-size: 30px;
}
.text-field-site {
  display: flex;
  margin-left: 2rem;
}

.text-field-user {
  margin-right: 2rem;
}
</style>
