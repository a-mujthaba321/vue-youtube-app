
<template>
  <div>
    <div class="row">
      <div class="col-md-2">
        <img 
          class="img-responsive"
          src="../../assets/images/youtubelogo-big.png">
      </div>
      <div 
        id="search-bar" 
        class="col-md-10">
        <input 
          placeholder="Search..." 
          @input="onInput">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(e) {
      this.$emit("searchTermChange", e.target.value);
    }
  }
};
</script>

<style scoped>
input {
  width: 100%;
}

img {
  max-width: 150px;
  margin-top: 20px;
  margin-bottom: 20px;
}

#search-bar {
  text-align: center;
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
