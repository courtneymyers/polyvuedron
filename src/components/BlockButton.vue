<template>
  <Button @click="$emit('button-clicked')">{{ text }}</Button>
</template>

<script>
import styled from 'vue-styled-components';

// styled components
const Button = styled.a`
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

  :hover,
  :focus {
    background-color: #360ccc;
  }
`;

export default {
  name: 'BlockButton',
  components: {
    // styled components
    Button,
  },
  props: {
    text: String
  },
}
</script>

<style scoped>
</style>
