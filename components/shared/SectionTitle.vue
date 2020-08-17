<template>
  <h3 class="section-title">{{titleProp}}</h3>
</template>

<script>
export default {
    name: "SectionTitle",
    props: {
        titleProp: {
            type: String,
            required: false
        } 
    }
}
</script>

<style>
.section-title {
  font-size: 3rem;
  margin-top: 4rem;
}
</style>