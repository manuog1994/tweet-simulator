<template>
  <Menu :openCloseForm="openCloseForm" :showForm="showForm" />
  <TweetForm :showForm="showForm" :reloadTweets="reloadTweets" :openCloseForm="openCloseForm"/>
  <TweetList :tweets="tweets" :reloadTweets="reloadTweets" />
</template>

<script>
import Menu from "./components/Menu.vue";
import TweetForm from "./components/TweetForm.vue";
import TweetList from "./components/TweetList.vue";
import useFormTweet from "./hooks/useFormTweet.js";
import { getTweetsApi } from "./api/tweet";
import {ref} from "vue";

export default {
  name: 'App',
  components: {
    Menu,
    TweetForm,
    TweetList,
  },

  setup() {
    let tweets = ref(getTweetsApi().reverse());

    const reloadTweets = () => {
      tweets.value = getTweetsApi().reverse();
    }

    return {
      ...useFormTweet(),
      tweets,
      reloadTweets,
    };
  },
};
</script>

<style lang="scss">

</style>
