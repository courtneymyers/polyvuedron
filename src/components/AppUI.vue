<template>
  <div class="container">
    <header class="header">
      <block-button
        class="block-button"
        text="☰"
        href="#library"
        title="Toggle Library"
        @anchor-clicked="toggleLeftPanel"
      />
      <h1 class="heading">Polyvuedron</h1>
      <block-button
        class="block-button"
        text="☰"
        href="#preview"
        title="Toggle Preview"
        @anchor-clicked="toggleRightPanel"
      />
    </header>

    <main class="main">
      <section class="section left-panel" v-if="leftPanelShown">
        <h2 class="subheading">Project Library</h2>
        <h2 class="subheading">Block Library</h2>
      </section>

      <section class="section middle-panel">
        <h2 class="subheading">Project Editor</h2>
      </section>

      <section class="section right-panel" v-if="rightPanelShown">
        <h2 class="subheading">Project Preview</h2>
      </section>
    </main>
  </div>
</template>

<script>
import BlockButton from './BlockButton.vue'

export default {
  name: 'AppUI',
  components: {
    BlockButton
  },
  data() {
    return {
      leftPanelShown: true,
      rightPanelShown: true,
    };
  },
  methods: {
    toggleLeftPanel() {
      event.preventDefault();
      this.leftPanelShown = !this.leftPanelShown;
    },
    toggleRightPanel() {
      event.preventDefault();
      this.rightPanelShown = !this.rightPanelShown;
    },
  },
}
</script>

<style scoped>
  .container {
    margin: 0 auto;
    max-width: 80rem;
  }

  .header {
    display: flex;
    padding: 1rem;
    background-color: #360a80;
  }

  .heading {
    flex: 1;
    margin: 0.1875rem 0.75rem 0;
    font-size: 1.3125rem;
    font-weight: normal;
    text-align: center;
    color: #fff;
  }

  .subheading {
    margin-top: 1rem;
    margin-bottom: 1rem;
    border-bottom: 1px solid #ccbee4;
    font-size: 1.125rem;
    color: #360a80;
  }
  .subheading:first-of-type {
    margin-top: 0;
  }

  .block-button {
    width: 1.5rem;
    height: 1.5rem;
    font-size: 1.125rem;
    line-height: 1.5rem;
    background-color: #60449a;
  }
  .block-button:hover,
  .block-button:focus {
    background-color: #60449a;
  }

  .main {
    display: flex;
    border: 1px solid #ccbee4;
    border-top: none;
  }

  .section {
    padding: 1rem;
  }

  .left-panel {
    flex: 0 0 15rem;
    border-right: 1px solid #ccbee4;
    background-color: #e2ddef;
  }

  .middle-panel {
    flex: 1;
    background-color: #edeaf3;
  }

  .right-panel {
    flex: 1;
    border-left: 1px solid #ccbee4;
    background-color: #e2ddef;
  }
</style>
