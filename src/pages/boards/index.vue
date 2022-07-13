<template>
  <TheNavbar> </TheNavbar>
  <button @click="addBoard">New Board +</button>
  <div>
    <section v-for="({ img, title }, index) in boards" :key="index">
      <img :src="img" alt="" />
      <h2>{{ title }}</h2>
      <router-link :to="`/boards/${index}`">
        <button>View</button>
      </router-link>
    </section>
  </div>
</template>
<script setup lang="ts">
// import { boards } from '../../data/boards.js'
import { ref } from "vue";
import TheNavbar from "../../components/TheNavbar.vue";
const boards = ref([
  { img: "https://placekitten.com/200/300", title: "Board 1" },

  { img: "https://placekitten.com/400/300", title: "Board 2" },
]);

const addBoard = () => {
  boards.value.push({
    img:
      "https://placekitten.com/" + 300 + "/" + Math.floor(Math.random() * 100),
    title: "Board " + (boards.value.length + 1),
  });
};
</script>
<style lang="postcss" scoped>
div {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
section {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  padding: 1rem;
}
</style>
