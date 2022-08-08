<script setup>
import { useRoute } from "vue-router";
import { ref, watch } from "vue";
import axios from "axios";

const route = useRoute();
const getData = ref("");
const img = ref("");

async function getFetchDataApi() {
  getData.value = null;
  const res = await axios.get(
    `https://api.nuxtjs.dev/posts/${route.params.id}`
  );
  getData.value = await res.data;

  console.log("*****", res.data);
}

getFetchDataApi();
</script>

<template>
  <main>
    <div class="container">
      <h1>{{ getData.title }}</h1>
      <p>
        {{ getData.description }}
      </p>
      <img :src="getData.image" alt="" />
    </div>
  </main>
</template>

<style lang="sass" scoped>
.container
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center

main
    min-height: 100vh
    padding-inline: 10%
    padding-top: 5% 
    margin: 0px
</style>