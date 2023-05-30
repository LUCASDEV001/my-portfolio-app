<template>
  <Navbar />
  <router-view />
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
  },
};
</script>

<style>
* {
  font-family: "Ysabeau", sans-serif;
  scroll-behavior: smooth;
}

::-webkit-scrollbar {
  width: 7px;
}

::-webkit-scrollbar-thumb {
  background-color: #ffca2c;
}
</style>
