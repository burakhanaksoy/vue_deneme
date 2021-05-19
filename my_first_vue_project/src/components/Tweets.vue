<template>
  <div id="user-tweet">
    <h2>Tweets</h2>
    <hr class="horizontal-ruler" />
    <div id="tweet" v-for="tweet in tweets" :key="tweet.id">
      <p class="each-tweet">{{ tweet.content }}</p>
      <button class="delete-tweet-btn" @click="deleteTweet">
        <i class="fas fa-trash"></i>
      </button>
    </div>
    <SubmitTweet @new_tweet="addTweet" />
  </div>
</template>

<script>
import SubmitTweet from "./SubmitTweet";
export default {
  name: "Tweets",
  components: { SubmitTweet },
  data() {
    return {
      tweets: [
        { content: "Hello world, this is my first tweet!" },
        { content: "Today was rainy in Istanbul.. Bummer! ://" },
      ],
    };
  },
  methods: {
    deleteTweet(event) {
      let childElement = event.target;
      childElement.parentElement.remove();
    },
    addTweet(text) {
      let newTweet = { content: "PlaceHolder" };
      newTweet.content = text;
      this.tweets.push(newTweet);
    },
  },
};
</script>

<style>
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css";
#user-tweet {
  display: flex;
  flex-direction: column;
  background: rgba(187, 187, 187, 0.342);
  width: 20rem;
  border-radius: 20px;
}
h2 {
  padding: 10px;
  margin-top: 1rem;
  background: aquamarine;
  border-radius: 20px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
.horizontal-ruler {
  margin-top: 0.5rem;
  border: 5px solid;
}
#tweet {
  font-family: sans-serif;
  color: rgb(142, 81, 192);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 1rem;
}
.each-tweet {
  margin-top: 1rem;
}
.delete-tweet-btn {
  margin-left: 0.5rem;
  padding: 0.5rem;
  cursor: pointer;
}
.fa-trash {
  pointer-events: none;
}
</style>