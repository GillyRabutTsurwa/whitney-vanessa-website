<template>

  <ul class="navigation__list">
    <li class="navigation__list--item">
      <a href="#">About</a>
    </li>
    <li class="navigation__list--item">
      <a href="#">Nutrition</a>
    </li>
    <li class="navigation__list--item">
      <a href="#">Fashion</a>
    </li>
    <li class="navigation__list--item">
      <a href="#">Reading</a>
    </li>
    <li class="navigation__list--item">
      <a href="#">Contact</a>
    </li>
  </ul>

</template>

<script>
export default {
  name: "Navigation"
}
</script>

<style lang="scss">
.navigation {
  &__list {
    position: absolute;
    top: 25%;
    left: 20.5%;
    list-style: none;

    font-size: 3.5rem;

    &--item {
      margin-bottom: 2rem;

      a {
        &:link,
        &:visited {
          text-decoration: none;
          color: rgb(21, 48, 52);
          padding: 0 2rem;
          border-left: 1.5px solid transparent;
          border-right: 1.5px solid transparent;

          transition: all 0.3s ease;
        }
        &:hover,
        &:active {
          border-left: 1.5px solid rgb(21, 48, 52);
          border-right: 1.5px solid rgb(21, 48, 52);
        }
      }
    }
  }
}
</style>