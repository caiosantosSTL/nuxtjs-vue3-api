<script setup>
import { RouterLink } from "vue-router";
import { ref, watch } from "vue";
import axios from "axios";

import Card from "../components/card/Card.vue";

const getData = ref("");
const img = ref("");

async function getFetchDataApi() {
  getData.value = null;
  const res = await axios.get("https://api.nuxtjs.dev/posts");
  getData.value = await res.data;

  console.log("*****", res.data);
}

getFetchDataApi();
</script>

<template>
  <main>
    <div class="title">
      <h1>The Mountains</h1>
    </div>

    <div class="container">
      <div v-for="data in getData" :key="data.id" >
      
        <Card
          :id="data.slug"
          :title="data.title"
          :description="data.description"
          :contriesA="data.countries[0]"
          :contriesB="data.countries[1]"
          :image="data.image"
        />
      </div>

    </div>
  </main>
</template>

<style lang="sass" scoped>
.title
  display: flex
  flex-direction: row
  justify-content: center
  height: 150px
  font-family: Arial, Helvetica, sans-serif
  padding: 2%
.container
  display: flex
  flex-direction: row
  flex-wrap: wrap
  justify-content: space-around
  padding-inline: 2%
main
  min-height: 100vh
</style>
