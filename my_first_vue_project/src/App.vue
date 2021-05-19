<template>
  <div id="mainPage">
    <UserProfile />
    <Tweets />
  </div>
  <!-- <div id="submit-btn">
    <SubmitTweet />
  </div> -->
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
  /* float: center; */
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
</style>
