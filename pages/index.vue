<template>
  <div>
    <h1>Batman TV Shows</h1>
    <ul>
      <li v-for="(item, index) in title" :key="index">
        <nuxt-link :to="{name:'post-id', params:{id: item.show.id}}">{{ item.show.name }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  asyncData() {
    return axios
      .get('https://api.tvmaze.com/search/shows?q=batman')
      .then(res => {
        return { title: res.data }
      })
  },
  methods: {},
  components: {}
}
</script>

<style>
li {
  list-style: none;
  margin: 5px 0;
}
a {
  text-decoration: none;
  color: blue;
  font-family: 'Arial';
}

a:hover {
  opacity: 0.6;
}
</style>
