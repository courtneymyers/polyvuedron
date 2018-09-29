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

    <main>
      <section class='left-panel' v-if='leftPanelShown'>
        <p>(Project and Block Libraries)</p>
      </section>

      <section class='middle-panel'>
        <p>(Project Editor)</p>
      </section>

      <section class='right-panel' v-if='rightPanelShown'>
        <p>(Project Preview)</p>
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

  main {
    display: flex;
    border: 1px solid #ccbee4;
    border-top: none;
  }

  section {
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
