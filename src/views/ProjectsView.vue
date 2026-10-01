<script setup>
import ProjectCard from '../components/ProjectCard.vue';
import animatedShowcase from '../assets/images/animated-product-showcase.png';
import artGallery from '../assets/images/art-galllery.png';
import foodFest from '../assets/images/food-fest-landing-page.png';
import jamn01 from '../assets/images/Jamn_01.png';
import jamn02 from '../assets/images/Jamn_02.png';
import rental from '../assets/images/rental-website.png';
import workforceLogin from '../assets/images/workforce-management-login.png';
import workforce from '../assets/images/workforce-management.png';

const projects = [
  { title: 'Jamn Music Discovery', icon: '♫', image: jamn01, hoverImage: jamn02, color: '#222222', tags: ['Vue.js', 'Node.js', 'Music UI'], description: 'A music streaming and artist discovery website built with Vue.js and Node.js, focused on browsing tracks, exploring artists, and delivering a smooth listening experience.', points: ['Music streaming experience', 'Artist discovery and exploration', 'Vue.js frontend with Node.js backend'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
  { title: 'Food Fest Landing Page', icon: '🍽', image: foodFest, color: '#d66a3a', tags: ['Vue', 'JavaScript', 'CSS'], description: 'A Vue-powered landing page for a food festival, designed to promote the event, highlight food experiences, and offer a polished mobile-friendly first impression.', points: ['Vue component-based interface', 'Responsive landing page layout', 'Food festival event promotion'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
  { title: 'Workforce Management Backend', icon: '⚙', image: workforceLogin, hoverImage: workforce, color: '#234f52', tags: ['Node.js', 'Express', 'MySQL', 'REST API'], description: 'An HR management backend for employees, departments, positions, attendance, payroll, leave requests, and permissions, built around clean API structure and database integration.', points: ['Express routes, controllers, and models', 'MySQL-backed data access', 'Centralized error handling middleware'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
  { title: 'Rental Website', icon: '⌂', image: rental, color: '#387a72', tags: ['HTML', 'CSS', 'JavaScript'], description: 'A rental property website presenting available homes and helping visitors explore rental options with a clean, modern layout and responsive user flow.', points: ['Property-focused landing page', 'Responsive visual layout', 'Clear rental browsing experience'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
  { title: 'Art Gallery Website', icon: '🖼', image: artGallery, color: '#e8d86b', tags: ['HTML', 'CSS', 'JavaScript'], description: 'A responsive image gallery with category-focused browsing for landscapes, portraits, and architecture, designed to showcase artwork in an elegant grid layout.', points: ['Gallery card grid', 'Category filter controls', 'Responsive image presentation'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
  { title: 'Animated Product Showcase', icon: '🎴', image: animatedShowcase, color: '#2d7a4a', tags: ['HTML', 'CSS', 'Flexbox'], description: 'A superhero-inspired product showcase featuring motion effects, hover states, and a modern storefront layout that highlights merchandise in a visually engaging way.', points: ['Flexbox product grid', 'CSS transitions and animations', 'Image overlays and hover effects'], github: 'https://github.com/totoseahlumile-dot', demo: 'https://github.com/totoseahlumile-dot/Portfolio' },
];
const concepts = [
  ['Vue.js', 'JavaScript Framework', 'Jamn Music Discovery, Food Fest Landing Page', 'Medium'],
  ['MySQL', 'Database', 'Workforce Management Backend', 'Medium'],
  ['Node.js', 'JavaScript Runtime', 'Jamn Music Discovery, Workforce Management Backend', 'Medium'],
  ['PHP', 'Programming Language', 'Backend Development', 'Growing'],
  ['Semantic HTML', 'HTML', 'All Projects', 'High'],
  ['HTML Forms & Input Types', 'HTML', 'Registration Form, Contact', 'Medium'],
  ['HTML Tables', 'HTML', 'Goals and exercises', 'High'],
  ['CSS Flexbox', 'CSS', 'Cards and navigation', 'Medium'],
  ['CSS Grid', 'CSS', 'Portfolio layouts', 'High'],
  ['Hover Effects & Transitions', 'CSS', 'Cards and buttons', 'High'],
  ['Responsive Design / Media Queries', 'CSS', 'Portfolio Website', 'Medium'],
  ['CSS Custom Properties (Variables)', 'CSS', 'Portfolio Website', 'Medium'],
  ['CSS Animations & Keyframes', 'CSS', 'Portfolio Website', 'Learning'],
];
</script>

<template>
  <div class="page-view" style="display: contents">
    <section class="page-hero"><div class="container"><p class="section-label">My Work</p><h1 class="section-title">Projects &amp; <em>Exercises</em></h1><p class="section-subtitle">A showcase of what I've built, practised, and learned throughout my web development course.</p></div></section>
    <section class="section"><div class="container"><p class="section-label">Featured Work</p><h2 class="section-title">What I've <em>Built</em></h2><div class="projects-grid"><ProjectCard v-for="project in projects" :key="project.title" :project="project" /></div></div></section>
    <section class="section" style="background:var(--clr-surface)"><div class="container"><p class="section-label">What I Practised</p><h2 class="section-title">Concepts <em>Used</em></h2><div class="goals-table-wrap"><table><thead><tr><th>Concept</th><th>Type</th><th>Used In</th><th>Confidence</th></tr></thead><tbody><tr v-for="concept in concepts" :key="concept[0]"><td>{{ concept[0] }}</td><td>{{ concept[1] }}</td><td>{{ concept[2] }}</td><td><span class="badge" :class="concept[3] === 'High' ? 'badge-done' : 'badge-progress'">{{ concept[3] }}</span></td></tr></tbody></table></div></div></section>
  </div>
</template>
