<template>
  <div>
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput(event) {
      this.$emit("termChanged", event.target.value);
    }
  }
};
</script>

<style scoped>
</style>