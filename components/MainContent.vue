<template>
  <div id="app">
    <Slider />
    <SectionTitle titleProp="About Whitney Vanessa" />
    <FirstSection />
    <SectionTitle titleProp="Yet Even More" />
    <SecondSection />
  </div>
</template>

<script>
import SectionTitle from "~/components/shared/SectionTitle";
import FirstSection from "~/components/FirstSection";
import SecondSection from "~/components/SecondSection";

export default {
  components: {
    SectionTitle: SectionTitle,
    FirstSection: FirstSection,
    SecondSection: SecondSection
  }
};
</script>

<style lang="scss">
// @import "./App.css";
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
