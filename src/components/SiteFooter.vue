<script setup>
const emit = defineEmits(['navigate']);

function navigate(page) {
  emit('navigate', page);
}
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <a href="#home" class="nav-logo" @click.prevent="navigate('home')">Ahlumile<span>Totose</span></a>
          <p>A beginner web developer building skills one project at a time.</p>
        </div>
        <div class="footer-col">
          <h4>Navigation</h4>
          <ul>
            <li><a href="#home" @click.prevent="navigate('home')">Home</a></li>
            <li><a href="#about" @click.prevent="navigate('about')">About Me</a></li>
            <li><a href="#projects" @click.prevent="navigate('projects')">Projects</a></li>
            <li><a href="#contact" @click.prevent="navigate('contact')">Contact</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Resources</h4>
          <ul>
            <li><a href="https://developer.mozilla.org">MDN Web Docs</a></li>
            <li><a href="https://github.com">GitHub</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2026 Ahlumile Totose.</p>
      </div>
    </div>
  </footer>
</template>
