<template>
  <div class="layout-style">
    <Header/>
    <nuxt/>
  </div>
</template>
<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  }
}
</script>
<style>
.layout-style {
  margin: 20px;
  padding: 20px;
  border: 1px solid #ddd;
}
</style>
