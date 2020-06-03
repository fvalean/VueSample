<template>
  <div id="app" class="container">
    <SearchBar @termChanged="onTermChange"></SearchBar>
    <div class="row">
      <div class="col-md-8">
        <VideoDetail :video="selectedVideo"></VideoDetail>
      </div>
      <div class="col-md-4">
        <VideoList :videos="videos" @videoSelect="onVideoSelect"></VideoList>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';

const API_KEY = process.env.VUE_APP_API_KEY;

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
    VideoDetail,
  },
  data() {
    return { videos: [], selectedVideo: null };
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(API_KEY);
      axios
        .get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: searchTerm,
          },
        })
        .then((response) => {
          this.videos = response.data.items;
        });
    },
    onVideoSelect(video) {
      this.selectedVideo = video;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
