<template>
  <div v-if="video">
    <div class="details">
      <h4 v-html="video.snippet.title"></h4>
      <p v-html="video.snippet.description"></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoDetail',
  props: ['video'],
};
</script>

<style scoped>
.details {
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>
