<template>
  <h2 @click="$emit('nav-toggle')" class="NuxtLogo">
    WV
  </h2>
</template>

<style>
.NuxtLogo {
  animation: 1s appear;
  font-size: 3.5rem;
  letter-spacing: -0.5rem;

  position: fixed;
  top: 2rem;
  left: 2rem;
  z-index: 1000;
  cursor: pointer;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
