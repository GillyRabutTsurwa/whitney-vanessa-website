<template>
  <div class="container">
    <Logo v-on:nav-toggle="toggleNav" />

    <transition-group name="fade" tag="div">
      <div v-for="currentValue in [currentIndex]" v-bind:key="currentValue" class="img-container" v-bind:style="setBackgroundImage">
      </div>
    </transition-group>

    <div v-if="!navShowing" class="heading appear">
      <h1>{{currentGreeting}}</h1>
      <h3>Welcome to My Site</h3>
      <Bouton>
        <span slot="text">Explore</span>
      </Bouton>
    </div>

    <Navigation v-else class="appear" />
  </div>
</template>

<script>
import Bouton from "./shared/Bouton";
import Navigation from "./Navigation";
import Logo from "./Logo";
export default {
  name: "Slider",
  components: {
    Bouton: Bouton,
    Navigation: Navigation,
    Logo: Logo
  },
  data() {
    return {
      timer: null,
      currentIndex: 0,
      images: [
        require("~/assets/img/nikita-tikhomirov-unsplash.jpg"),
        require("~/assets/img/annie-spratt-unsplash.jpg"),
        require("~/assets/img/zibik-unsplash.jpg") 
      ],
      greetings: ["Hello", "Wassup", "Welcome"],
      navShowing: false
    };
  },
  methods: {
    next() {
      this.currentIndex += 1;
      // if (this.currentIndex > this.images.length - 1) {
      //   this.currentIndex = 0;
      // }
    },
    prev() {
      this.currentIndex -= 1;
    },
    startSlide() {
      // NOTE: timer variable ne fait rien en fait.
      // this.timer = setInterval(this.next, 4000);
      setInterval(this.next, 6000);
    },
    toggleNav() {
      this.navShowing = !this.navShowing;
      console.log("I WAS LIKCSED")
    }
  },
  computed: {
    currentImg: function() {
      //TESTING:
      // return this.images[this.currentIndex];
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    },
    setBackgroundImage: function() {
      return {
        backgroundImage: `linear-gradient(105deg, rgba(255, 255, 255, 0.9) 0%, rgba(255, 255, 255, 0.9) 50%, transparent 50%) , url('${this.currentImg}')` 
      }
    },
    currentGreeting: function() {
      return this.greetings[
        Math.abs(this.currentIndex) % this.greetings.length
      ];
    }
  },
  mounted() {
    this.startSlide();
  }
};
</script>

<style scoped lang="scss">
.container {
  position: relative;
  width: 100%;
  height: 93vh;
}

.heading {
  position: absolute;
  top: 30%;
  display: block;
  width: 50%;

  h1 {
    font-size: 7rem;
  }

  h3 {
    margin-bottom: 2rem;
  }
}

.img-container {
  width: 100%;
  height: 100vh;
  background-size: cover;
  background-position: center;
  position: relative;
  // background-image: linear-gradient(
  //     105deg,
  //     rgba(255, 255, 255, 0.9) 0%,
  //     rgba(255, 255, 255, 0.9) 50%,
  //     transparent 50%
  //   ),
  //   url(../assets/img/nikita-tikhomirov-unsplash.jpg);
}

/* .myImg {
  width: 100%;
  height: 100%;
} */

.fade-enter-active {
  animation-name: fadeEnter;
  animation-duration: 2s;
  animation-iteration-count: 1;
}
.fade-move {
  transition: all 2s;
}
.fade-leave-active {
  animation-name: fadeLeave;
  animation-duration: 2s;
  animation-iteration-count: 1;
  position: absolute;
}

.appear {
  animation: appear 1s;
}

@keyframes fadeEnter {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeLeave {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>