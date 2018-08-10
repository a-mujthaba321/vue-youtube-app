<template>
  <div class="container">
    <SearchBar @searchTermChange="onSearchTermChange"/>
    <VideoList :videos="videos"/> 
  </div>
</template>
<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
const YOUTUBE_KEY = "AIzaSyCXhMsWNEYzzWlWtlK2nqGWN7eGncsGPyg";
export default {
  name: "App",
  components: {
    SearchBar,
    VideoList
  },
  data() {
    return {
      videos: []
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
    }
  }
};
</script>
