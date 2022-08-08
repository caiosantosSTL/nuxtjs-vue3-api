<script setup>
import { RouterLink } from "vue-router";
const props = defineProps({
  id: String,
  title: String,
  description: String,
  contriesA: String,
  contriesB: String,
  image: String,
});
</script>

<template>
  <div class="card">
    <div class="title">
      <h2>
        <RouterLink id="link" :to="{ path: '/detail/' + id }">{{
          title || "No value"
        }}</RouterLink>
      </h2>
    </div>

    <p>Description: {{ description || "" }}</p>
    <p>Country: {{ contriesA || "" }} | {{ contriesB || "" }}</p>
    <div class="image">
      <img :src="image" alt="" />
    </div>
  </div>
</template>

<style lang="sass" scoped>
$navcolor-a: #1f1019
$navcolor-btn: #736942
$text-color: #fffff0

.title
  display: flex
  justify-content: center
  align-content: center
.card
  display: flex
  flex-direction: column
  flex-wrap: nowrap
  margin-top: 20px
  margin-left: 20px
  border-radius: 10px
  padding: 15px
  max-width: 400px
  min-height: 500px
  font-family: Arial, Helvetica, sans-serif

  color: $text-color
  background-color: $navcolor-a
  .image
    display: flex
    justify-content: center
    img
      height: 200px
      width: 300px
      border-radius: 10px

  #link
    text-decoration: none
    color: white
    &:hover
      color: #c2c2c2
</style>