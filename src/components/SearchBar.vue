<template>
  <div>
    <input type="text" @input="onSearch" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onSearch(e) {
      this.$emit("termChange", e.target.value);
    },
  },
};
</script>

<style></style>
