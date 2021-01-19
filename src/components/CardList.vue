<template>
  <div class="cardList">
    <Card
      v-for="(post, index) in posts"
      v-bind="post" 
      :key="index" /> 
  </div>
</template>

<script>
import Card from './Card.vue';
import axios from 'axios';
import { getSomeText } from '../utils/index';

export default {
  name: 'CardList',
  components: {
    Card
  },
  data() {
    return {
      posts: []
    };
  },
  created() {
    this.getImgs();
  },
  methods: {
    getImgs() {
      axios
        .get('https://pixabay.com/api/?key=19943135-85888d8de5db7a300a292d074')
        .then((res) => {
          const newPosts = res.data.hits.map((d) => ({
            username: 'user_skmr',
            img: d.largeImageURL,
            text: getSomeText(),
          }));
          this.posts = newPosts;
        })
        .catch((err) => console.error(err));
    }
  }
}
</script>

<style>

</style>