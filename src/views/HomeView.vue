<script setup>
import { ref } from 'vue'
import TheWelcome from '../components/TheWelcome.vue'

// Example state for controlling the start of the game
const gameStarted = ref(false)

const startGame = () => {
  gameStarted.value = true
}
</script>

<template>
  <div class="welcome-container">
    <h1>NIGHTFALL</h1>

    <!-- Welcome Message -->
    <p class="intro-text">
      Welcome to Nightfall, a thrilling multiplayer game where villagers must survive the night, 
      and werewolves hunt their prey. Can you uncover the truth before it's too late?
    </p>

    <!-- Game Instructions -->
    <div class="instructions">
      <h2>How to Play:</h2>
      <ul>
        <li>Join a room or create your own to begin.</li>
        <li>During the night, werewolves will secretly choose a victim.</li>
        <li>During the day, villagers vote to eliminate a suspect.</li>
        <li>Can the villagers find the werewolves before it's too late?</li>
      </ul>
    </div>

    <!-- Start Game Button -->
    <button @click="startGame" class="start-game-btn">Start Game</button>

    <!-- Display once the game starts -->
    <div v-if="gameStarted" class="game-started">
      <p>The game is starting... Prepare for Nightfall!</p>
    </div>
  </div>
</template>

<style scoped>
.welcome-container {
  text-align: center;
  margin-top: 50px;
  color: #fff;
  background-color: #121212;
  padding: 20px;
  border-radius: 10px;
}

h1 {
  font-size: 3rem;
  margin-bottom: 20px;
  color: #e63946;
}

.intro-text {
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.instructions h2 {
  font-size: 1.8rem;
  margin-bottom: 10px;
}

.instructions ul {
  list-style-type: disc;
  padding-left: 20px;
  text-align: left;
}

.start-game-btn {
  background-color: #e63946;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.2rem;
}

.start-game-btn:hover {
  background-color: #d62839;
}

.game-started {
  margin-top: 20px;
  font-size: 1.4rem;
  color: #fff;
}
</style>
