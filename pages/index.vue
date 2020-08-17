<template>
  <div id="app">
    <transition name="fade" mode="out-in">
      <component v-bind:is="component">
      </component>
    </transition>
  </div>
</template>

<script>
import Loader from "../components/Loader";
import MainContent from "../components/MainContent";
export default {
  components: {
    Loader: Loader,
    MainContent: MainContent
  },
  data() {
    return {
      component: "Loader"
    };
  },
  mounted() {
    window.addEventListener("load", () => { 
      setTimeout(() => {
        this.component = "MainContent";
      }, 5000);
    });
  }
};
</script>

<style lang="scss">
// @import url(../static/index.css);
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

.fade-enter-active {
  transition: all 0.4s;
}
.fade-enter {
  opacity: 0;
}
.fade-leave-active {
  transition: all 0.4s;
  opacity: 0;
}
</style>