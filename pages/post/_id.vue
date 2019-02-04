<template>
  <div>
    <h1>{{post.name}}</h1>
    <p v-html="summary">{{summary}}</p>
    <img :src="post.image.medium">
  </div>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ params }) {
    return axios.get(`https://api.tvmaze.com/shows/${params.id}`).then(res => {
      return {
        post: res.data,
        summary: res.data.summary.replace(/<[/]?p>/g, '')
      }
    })
  },
  data: function() {}
}
</script>
