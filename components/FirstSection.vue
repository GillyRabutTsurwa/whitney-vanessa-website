<template>
  <section class="section-juan">
    <div class="whito-image-container">
      <img src="~/assets/img/whito-1.jpeg" alt="">
    </div>
    <div class="about-whito-text">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. At velit aliquid tempore, rem deserunt doloremque mollitia recusandae error laborum fugit! Atque quasi magni explicabo ipsam molestiae? Debitis natus deleniti vitae nostrum voluptatem assumenda placeat architecto aspernatur facere! Laborum nemo omnis praesentium voluptas necessitatibus explicabo saepe odit. Voluptatum, architecto soluta. Voluptates.
    </div>
  </section>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.section-juan {
  padding: 0 3.5rem;
  display: flex;
  justify-content: center;
}
.whito-image-container {
  position: relative;
  width: 50rem;
  height: 60rem;
  background-position: top;
  background-size: cover;

  //DARK OVERLAY
  &::after {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
    z-index: 100;
  }

  & img {
    width: 100%;
    height: 100%;
  }
}
.about-whito-text {
  width: 40%;
}
</style>