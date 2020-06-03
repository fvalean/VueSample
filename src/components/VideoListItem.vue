<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img :src="thumbnailUrl" class="mr-3" />
    <div class="media-body">
      <h5 class="mt-0 mb-1" v-html="video.snippet.title"></h5>
    </div>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video'],
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    },
  },
  methods: {
    onVideoSelect() {
      this.$emit('videoSelect', this.video);
    },
  },
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
}

li:hover {
  background-color: #ddd;
}
</style>
