<template>
  <ul class="list-group">
    <VideoItem 
      v-for="video in videos"
      :video="video"
      :key="video.etag"   
    />
  </ul> 
</template>


<script>
import VideoItem from "./VideoItem";
export default {
  name: "VideoList",
  components: { VideoItem },
  props: {
    videos: Array
  }
};
</script>


<style>
</style>
