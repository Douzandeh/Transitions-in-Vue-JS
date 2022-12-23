<script setup></script>

<template>
  <div>
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "montserrat", sans-serif;
}

nav {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1rem;
}

nav a {
  margin: 0 0.5rem;
  color: black;
  text-decoration: none;
}

nav a:hover,
nav a.router-link-exact-active {
  color: crimson;
  text-decoration: underline;
}

.check {
  display: flex;
  align-items: center;
  justify-content: center;
}

.check label {
  margin: 0 0.5rem;
}

main {
  padding: 1rem;
  max-width: 768px;
  margin: 0 auto;
  will-change: transform, opacity;
}

h1 {
  margin-bottom: 1.5rem;
}

p {
  margin-bottom: 1rem;
}

img {
  width: 100%;
  max-width: 100%;
  margin-bottom: 1.5rem;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-out;
}
</style>
