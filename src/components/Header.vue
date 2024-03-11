<template>
  <section class="header">
    <div class="header-content">
      <h1>{{ heroMessage }}</h1>
      <div class="button">
        <button class="button2" @click="handleClickAndToggleVisibility">
          Click Me
        </button>
        <p v-if="isVisible">This is a Vanilla page I edited using Vue!</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

// Data Binding practice - calling from script
const heroMessage = ref("Hello, welcome to my page!");
const isVisible = ref(true);

// Events handling using buttons
const handleClickAndToggleVisibility = () => {
  handleClick();
  toggleVisibility();
};

const handleClick = () => {
  console.log("Button clicked!");
};

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
</script>

<style scoped>
.header {
  background-image: url("https://images.pexels.com/photos/414659/pexels-photo-414659.jpeg");
  background-size: 100%; /* Make the background image cover the entire width */
  background-position: center;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.header-content {
  text-align: center;
  color: black;
}

.button2 {
  margin-top: 20px;
  background-color: gray;
  color: white;
}

@media (max-width: 768px) {
  .header-content {
    flex-direction: column;
  }
}
</style>
