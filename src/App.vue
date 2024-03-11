<script setup>
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";
import { ref } from "vue";

//Nav Bar: Component 1
const routes = [
  { path: "/", component: Home },
  { path: "/about", component: About },
  { path: "/contact", component: Contact },
];

//Data Binding practice - calling from script
const heroMessage = "Hello, welcome to my page!";
const isVisible = ref(true);

//Component 2: Button
//Conditional Ex using Buttons
const handleClickAndToggleVisibility = () => {
  handleClick();
  toggleVisibility();
};

//Events handling using buttons
const handleClick = () => {
  console.log("Button clicked!");
};

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
</script>

<template>
  <nav>
    <ul>
      <router-link to="#">Home</router-link>
      <router-link to="/components/About.vue">About</router-link>
      <router-link to="/components/Contact.vue">Contact</router-link>
    </ul>
  </nav>

  <section class="header">
    <h1>{{ heroMessage }}</h1>

    <div class="button">
      <button class="button2" @click="handleClickAndToggleVisibility">
        Click Me
      </button>

      <p v-if="isVisible">This is a Vanilla page I edited using Vue!</p>
    </div>
  </section>
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

.header {
  background-image: url("https://images.pexels.com/photos/414659/pexels-photo-414659.jpeg");
  background-size: cover;
  background-position: center;
  height: 500px;
  width: 140%;
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  color: black;
  text-align: center;
  flex-direction: column;
  align-items: center;
}

.button2 {
  justify-content: center;
  margin-top: 10px;
  padding: 30px, 30px;
  background-color: #333;
  color: white;
}

.button button:hover {
  cursor: pointer;
  background-color: lightgrey;
  color: black;
}
</style>
