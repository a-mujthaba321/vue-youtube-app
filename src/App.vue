

<template>
<div>
    <SearchBar @searchTermChange="onSearchTermChange"/>
</div>
</template>
<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
const YOUTUBE_KEY = "AIzaSyCXhMsWNEYzzWlWtlK2nqGWN7eGncsGPyg";
export default {
  name: "App",
  components: {
    SearchBar
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
          console.log(response);
        });
    }
  }
};
</script>
