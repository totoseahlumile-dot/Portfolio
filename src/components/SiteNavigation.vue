<script setup>
import { ref } from 'vue';

defineProps({
  currentPage: {
    type: String,
    required: true,
  },
});

const emit = defineEmits(['navigate']);
const mobileNavOpen = ref(false);

function navigate(page) {
  mobileNavOpen.value = false;
  emit('navigate', page);
}
</script>

<template>
  <div class="site-navigation">
    <nav class="navbar" role="navigation" aria-label="Main navigation">
      <div class="container nav-inner">
        <a href="#home" class="nav-logo" @click.prevent="navigate('home')">Ahlumile<span>Totose</span></a>
        <ul class="nav-links" role="list">
          <li><a href="#home" :class="{ active: currentPage === 'home' }" @click.prevent="navigate('home')">Home</a></li>
          <li><a href="#about" :class="{ active: currentPage === 'about' }" @click.prevent="navigate('about')">About</a></li>
          <li><a href="#projects" :class="{ active: currentPage === 'projects' }" @click.prevent="navigate('projects')">Projects</a></li>
          <li><a href="#contact" :class="{ active: currentPage === 'contact' }" @click.prevent="navigate('contact')">Contact</a></li>
        </ul>
        <a href="#contact" class="btn btn-primary nav-cta desktop-only" @click.prevent="navigate('contact')">Say Hello</a>
        <button class="hamburger" type="button" aria-label="Toggle menu" :aria-expanded="mobileNavOpen" @click="mobileNavOpen = !mobileNavOpen">
          <span></span><span></span><span></span>
        </button>
      </div>
    </nav>

    <div class="mobile-nav" :class="{ open: mobileNavOpen }" role="navigation" aria-label="Mobile navigation">
      <a href="#home" @click.prevent="navigate('home')">Home</a>
      <a href="#about" @click.prevent="navigate('about')">About Me</a>
      <a href="#projects" @click.prevent="navigate('projects')">Projects</a>
      <a href="#contact" @click.prevent="navigate('contact')">Contact</a>
    </div>
  </div>
</template>

<style scoped>
.site-navigation {
  display: contents;
}
</style>
