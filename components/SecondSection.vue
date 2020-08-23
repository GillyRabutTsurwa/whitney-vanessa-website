//NEW:
<template>
  <section class="section-two">
    <div class="left">
      <div v-if="current === 'Designer'" class="left__title-text">
        <h3 class="left__title-text--title">{{info[0]}}</h3>
        <p class="left__title-text--text">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum unde rerum, minima, deleniti numquam, suscipit cupiditate ex mollitia hic ullam assumenda architecto est molestiae autem inventore eius commodi ducimus debitis!
        </p>
      </div>

      <div v-else-if="current === 'Creator'" class="left__title-text">
        <h3 class="left__title-text--title">{{info[1]}}</h3>
        <p class="left__title-text--text">Placeat accusantium expedita necessitatibus, iste beatae sequi fugit debitis, perferendis ullam pariatur, quod velit impedit cum consequatur sunt quisquam provident quibusdam ipsum!
        </p>
      </div>

      <div v-else-if="current === 'Mentor'" class="left__title-text">
        <h3 class="left__title-text--title">{{info[2]}}</h3>
        <p class="left__title-text--text">
          Nulla, dolore fuga unde in debitis officia distinctio facere assumenda, dolorem quia atque sequi velit error at iure maiores recusandae dicta! Hic?
        </p>
      </div>

    </div>
    <div class="right">
      <div v-on:click="current = currentValue" v-for="(currentValue, index) in info" v-bind:key="index" v-bind:style="{backgroundImage: `url('${images[index]}')`}" class="right__thumbnail">
        <h3>{{currentValue}}</h3>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FirstSection",
  data() {
    return {
      info: ["Designer", "Creator", "Mentor"],
      current: "Designer",
      images: [
        require("~/assets/img/nikita-tikhomirov-unsplash.jpg"),
        require("~/assets/img/annie-spratt-unsplash.jpg"),
        require("~/assets/img/zibik-unsplash.jpg")
      ]
    };
  }
};
</script>

<style lang="scss">
.section-two {
  display: flex;
  margin-top: 5rem;
  // padding: 0 3rem;
  .left {
    flex: 0 0 60%;
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    &__title-text {
      &--title {
        font-size: 3rem;
        margin-bottom: 4rem;
      }
      &--text {
        text-align: left;
        text-indent: 3rem;
        font-size: 2rem;
        margin: 0 2rem;
      }
    }
  }
  .right {
    flex: 0 0 40%;
    display: flex;
    flex-direction: column;
    cursor: pointer;
    padding-right: 2rem;
    &__thumbnail {
      display: flex;
      justify-content: center;
      align-items: center;
      color: #fff;
      margin-bottom: 2rem;
      // background-color: rgb(255, 80, 89);
      background-size: cover;
      height: 20rem;
    }
  }
}
</style>