<template>
  <div>
    <header>
      <block-button
        text='☰'
        href='#library'
        title='Toggle Library'
        @anchor-clicked='toggleLeftPanel()'
      />
      <h1>Polyvuedron</h1>
      <block-button
        text='☰'
        href='#preview'
        title='Toggle Preview'
        @anchor-clicked='toggleRightPanel()'
      />
    </header>
  </div>
</template>

<script>
import BlockButton from './BlockButton.vue'

export default {
  name: 'AppUI',
  components: {
    BlockButton
  },
  methods: {
    toggleLeftPanel() {
      event.preventDefault();
      console.log('Library Panel toggled.')
    },
    toggleRightPanel() {
      event.preventDefault();
      console.log('Preview Panel toggled.')
    },
  },
}
</script>

<style scoped>
  div {
    margin: 0 auto;
    max-width: 80rem;
  }

  header {
    display: flex;
    padding: 1rem;
    background-color: #360a80;
  }

  h1 {
    flex: 1;
    margin: 0.1875rem 0.75rem 0;
    font-size: 1.3125rem;
    font-weight: normal;
    text-align: center;
    color: #fff;
  }

  a {
    width: 1.5rem;
    height: 1.5rem;
    font-size: 1.125rem;
    line-height: 1.5rem;
    background-color: #60449a;
  }
  a:hover,
  a:focus {
    background-color: #60449a;
  }
</style>
