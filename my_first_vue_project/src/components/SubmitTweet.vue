<template>
  <form id="form">
    Tweet<input id="input-box" type="text" />
    <button id="tweet-btn" @click="addNewTweet">Tweet</button>
  </form>
</template>

<script>
export default {
  name: "SubmitTweet",
  methods: {
    addNewTweet(event) {
      event.preventDefault();
      let text = document.getElementById("input-box").value;
      this.$emit("new_tweet", text);
    },
  },
};
</script>

<style>
#form {
  display: flex;
  flex-direction: column;
  margin: 1rem;
  align-items: center;
  /* justify-content: center; */
}

#input-box {
  width: 20rem;
}
#tweet-btn {
  margin-top: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 10rem;
  height: 1.5rem;
  background-color: rgb(137, 151, 212);
  border-radius: 15px;
  cursor: pointer;
  font-size: 20px;
}
</style>