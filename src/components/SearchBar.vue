
<template>
    <div>
        <input @input="onInput"/>
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

<style>
</style>
