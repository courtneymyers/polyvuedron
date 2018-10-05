<template>
  <Container>
    <Header>
      <ToggleButton
        text="☰"
        href="#library"
        title="Toggle Library"
        @click.prevent="toggleLeftPanel"
      />
      <Heading>Polyvuedron</Heading>
      <ToggleButton
        text="☰"
        href="#preview"
        title="Toggle Preview"
        @click.prevent="toggleRightPanel"
      />
    </Header>

    <Main>
      <LeftPanel v-if="leftPanelShown">
        <SubHeading>Project Library</SubHeading>
        <SubHeading>Block Library</SubHeading>
      </LeftPanel>

      <MiddlePanel>
        <SubHeading>Project Editor</SubHeading>
      </MiddlePanel>

      <RightPanel v-if="rightPanelShown">
        <SubHeading>Project Preview</SubHeading>
      </RightPanel>
    </Main>
  </Container>
</template>

<script>
import styled from 'vue-styled-components';
import BlockButton from './BlockButton.vue';

// styled components
const Container = styled.div`
  margin: 0 auto;
  max-width: 80rem;
`;

const Header = styled.header`
  display: flex;
  padding: 1rem;
  background-color: #360a80;
`;

const ToggleButton = styled(BlockButton)`
  width: 1.5rem;
  height: 1.5rem;
  font-size: 1.125rem;
  line-height: 1.5rem;
  background-color: #60449a;

  :hover,
  :focus {
    background-color: #60449a;
  }
`;

const Heading = styled.h1`
  flex: 1;
  margin: 0.1875rem 0.75rem 0;
  font-size: 1.3125rem;
  font-weight: normal;
  text-align: center;
  color: #fff;
`;

const Main = styled.main`
  display: flex;
  border: 1px solid #ccbee4;
  border-top: none;
`;

const Panel = styled.section`
  padding: 1rem;
`;

const SubHeading = styled.h2`
  margin-top: 1rem;
  margin-bottom: 1rem;
  border-bottom: 1px solid #ccbee4;
  font-size: 1.125rem;
  color: #360a80;

  :first-of-type {
    margin-top: 0;
  }
`;

const LeftPanel = Panel.extend`
  flex: 0 0 15rem;
  border-right: 1px solid #ccbee4;
  background-color: #e2ddef;
`;

const MiddlePanel = Panel.extend`
  flex: 1;
  background-color: #edeaf3;
`;

const RightPanel = Panel.extend`
  flex: 1;
  border-left: 1px solid #ccbee4;
  background-color: #e2ddef;
`;

export default {
  name: 'AppUI',
  components: {
    // styled components
    Container,
    Header,
    ToggleButton,
    Heading,
    Main,
    Panel,
    SubHeading,
    LeftPanel,
    MiddlePanel,
    RightPanel,
  },
  data() {
    return {
      leftPanelShown: true,
      rightPanelShown: true,
    };
  },
  methods: {
    toggleLeftPanel() {
      this.leftPanelShown = !this.leftPanelShown;
    },
    toggleRightPanel() {
      this.rightPanelShown = !this.rightPanelShown;
    },
  },
};
</script>

<style scoped>
</style>
