<template>
  <div class="container">
    <SearchBar 
      @searchTermChange="onSearchTermChange" 
    />
    <div class="row">
      <VideoDetail 
        :video="selectedVideo" 
      />
      <VideoList 
        :videos="videos"
        @videoChange="onVideoChange"
      /> 
    </div>
  </div>
</template>
<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";
const YOUTUBE_KEY = "AIzaSyCXhMsWNEYzzWlWtlK2nqGWN7eGncsGPyg";
export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  data() {
    return {
      videos: [],
      selectedVideo: {}
    };
  },
  methods: {
    onSearchTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: YOUTUBE_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(response => {
          this.videos = response.data.items;
        });
    },

    onVideoChange(video) {
      console.log(video);
      this.selectedVideo = video;
    }
  }
};
</script>
