<template>
  <a class='block-button' @click='$emit(`anchor-clicked`)'>{{ text }}</a>
</template>

<script>
export default {
  name: 'BlockButton',
  props: {
    text: String
  },
}
</script>

<style scoped>
.block-button {
  display: block;
  width: 1.25rem;
  height: 1.25rem;
  border-radius: 3px;
  font-size: 1rem;
  line-height: 1.25rem;
  font-weight: bold;
  color: #fff;
  background-color: #360a80;
  text-align: center;
  text-decoration: none;
  user-select: none;
}
.block-button:hover,
.block-button:focus {
  background-color: #360ccc;
}
</style>
