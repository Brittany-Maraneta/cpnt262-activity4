<script setup>
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import { ref } from "vue";

// Nav Bar: Component 1
const routes = [
  { path: "/", component: Home },
  { path: "/about", component: About },
  { path: "/contact", component: Contact },
];
</script>

<template>
  <nav>
    <ul>
      <router-link to="#">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/contact">Contact</router-link>
    </ul>
  </nav>

  <Header />
  <Main />
</template>

<style scoped>
body {
  margin: 0;
  padding: 0;
}

nav {
  background-color: #333;
  color: #fff;
  padding: 10px;
  width: 100%;
  position: fixed;
  top: 0;
  margin-left: auto;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

nav ul router-link {
  margin-right: 15px;
  margin-left: 15px;
}

nav ul router-link a {
  color: #fff;
  text-decoration: none;
}
</style>
