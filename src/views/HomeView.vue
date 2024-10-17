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
  <div class="app-container">
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
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #1d1b1b;
}

/* Styles for the welcome content */
.welcome-container {
  text-align: center;
  color: #fff;
  background-color: #121212;
  padding: 20px;
  border-radius: 10px;
  max-width: 500px;
}

/* Heading styles */
h1 {
  font-size: 3rem;
  margin-bottom: 20px;
  color: #e63946;
}

/* Introduction text */
.intro-text {
  font-size: 1.5rem;
  margin-bottom: 20px;
}

/* Instructions */
.instructions h2 {
  font-size: 1.8rem;
  margin-bottom: 10px;
}

.instructions ul {
  list-style-type: disc;
  padding-left: 20px;
  text-align: left;
}

/* Start Game Button */
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

/* Game started message */
.game-started {
  margin-top: 20px;
  font-size: 1.4rem;
  color: #fff;
}

/* Responsive Design for larger screens */
@media (min-width: 1024px) {
  .app-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .welcome-container {
    max-width: 600px;
  }
}
</style>
