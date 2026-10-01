<script setup>
import { ref } from 'vue';
import portrait from '../assets/images/IMG_1999.jpg';

const emit = defineEmits(['navigate']);
const skills = [
  { title: 'HTML', rows: [['Document Structure', 85], ['Semantic Elements', 80], ['Forms & Tables', 75]] },
  { title: 'CSS', rows: [['Selectors & Box Model', 80], ['Flexbox & Grid', 75], ['Responsive Design', 70]] },
  { title: 'JavaScript', rows: [['Syntax & Basics', 65], ['Objects & Functions', 60], ['DOM & Event Logic', 55]] },
  { title: 'Vue', rows: [['Component Structure', 60], ['Props & State', 55], ['Routing & Layouts', 50]] },
  { title: 'PHP', rows: [['Logic & Forms', 50], ['Backend Basics', 45], ['Data Handling', 40]] },
  { title: 'Python', rows: [['Syntax & Basics', 70], ['Basic Scripting', 65], ['Problem Solving', 60]] },
];
const tools = ['VS Code', 'GitHub', 'Git', 'Figma', 'Terminal', 'Vue Router', 'MySQL'];
const interests = [
  { label: 'Gaming', image: 'https://www.konami.com/games_cms/promo/eu/uploads/efootball_v550_keyvisual_4k-1024x576.png' },
  { label: 'Anime', image: 'https://m.media-amazon.com/images/I/5138ZM+0GpL._SY445_SX342_ML2_.jpg' },
  { label: 'Reading', image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSL2OktXBpBiH9x--ohcme9wFlJc23snjRJKQ&s' },
  { label: 'Music Production', image: 'https://slimegreenbeats.com/cdn/shop/articles/thumbnail_8e1f0c46-2f57-4b68-a7bf-fae8faeab56b.jpg?v=1737201081' },
  { label: 'Wild Animals', image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcShN_cyGL4GyqcSEBc5_e3BmBtDTfE826YFQQ&s' },
  { label: 'Playing Football', image: 'https://one10sport.co.za/wp-content/uploads/2023/07/one10sport-football-academy-player-1024x344.webp' },
];
const goals = [
  ['HTML Fundamentals', 'HTML', 'Month 1', 'Done', 'Semantic structure, forms, content layout'],
  ['CSS Foundations', 'CSS', 'Month 1', 'Done', 'Spacing, colours, typography, and layout basics'],
  ['Responsive Web Design', 'CSS', 'Month 2', 'Done', 'Mobile-friendly layouts and flexible grids'],
  ['JavaScript Foundations', 'JavaScript', 'Month 3', 'Done', 'Variables, functions, logic, and DOM basics'],
  ['Vue.js Fundamentals', 'Vue', 'Month 4', 'In Progress', 'Components, props, and reusable UI patterns'],
  ['PHP + Forms', 'PHP', 'Month 5', 'In Progress', 'Handling form logic and backend interactions'],
  ['Database Basics', 'MySQL', 'Month 5', 'In Progress', 'Tables, queries, and data relationships'],
  ['Portfolio Deployment', 'Deployment', 'Month 6', 'In Progress', 'Polish and publish a live portfolio project'],
];
</script>

<template>
  <div class="page-view" style="display: contents">
    <section class="hero" id="hero" aria-labelledby="hero-heading">
      <div class="container"><div class="hero-grid">
        <div class="hero-text">
          <div class="hero-eyebrow">Junior Full Stack Developer</div>
          <h1 class="hero-name" id="hero-heading">Hello, I'm <em>Ahlumile Totose</em></h1>
          <p class="hero-tagline">A curious developer learning to build beautiful, functional web experiences with a growing foundation in design, logic, and user experience.</p>
          <div class="hero-btns"><a href="#projects" class="btn btn-primary" @click.prevent="emit('navigate', 'projects')">View My Work</a><a href="#about" class="btn btn-outline" @click.prevent="emit('navigate', 'about')">Learn About Me</a></div>
          <div class="hero-stats"><div><div class="stat-num">8+</div><div class="stat-label">Projects Built</div></div><div><div class="stat-num">6+</div><div class="stat-label">Languages Learned</div></div><div><div class="stat-num">100%</div><div class="stat-label">Passion</div></div></div>
        </div>
        <div class="hero-visual" aria-hidden="true"><div class="hero-img-wrap"><div class="hero-img-bg"></div><div class="hero-img-placeholder"><img :src="portrait" alt="Ahlumile Totose" class="hero-avatar-img" /></div></div></div>
      </div></div>
    </section>
    <section class="section skills-section" aria-labelledby="skills-heading"><div class="container"><p class="section-label">What I Know</p><h2 class="section-title" id="skills-heading">My <em>Skills</em> So Far</h2><p class="section-subtitle">I'm still growing, but I'm building a strong foundation in web development, problem-solving, and creating practical digital experiences.</p><div class="skills-grid"><article v-for="skill in skills" :key="skill.title" class="skill-category"><h3 class="skill-cat-title">{{ skill.title }}</h3><div class="skill-bars"><div v-for="row in skill.rows" :key="row[0]" class="skill-row"><div class="skill-row-top"><span>{{ row[0] }}</span><span>{{ row[1] }}%</span></div><div class="skill-bar-bg"><div class="skill-bar-fill" :style="{ width: `${row[1]}%` }"></div></div></div></div></article><article class="skill-category"><h3 class="skill-cat-title">Tools &amp; Workflow</h3><div class="tech-tags"><span v-for="tool in tools" :key="tool" class="tech-tag">{{ tool }}</span></div></article></div></div></section>
    <section class="section interests-section"><div class="container"><p class="section-label">Beyond Code</p><h2 class="section-title">My <em>Interests</em></h2><p class="section-subtitle">When I'm not writing code, here's what keeps me inspired and energised.</p><div class="interests-grid"><div v-for="interest in interests" :key="interest.label" class="interest-card" role="listitem"><div class="interest-card-inner"><img :src="interest.image" :alt="interest.label" class="interest-card-img" /><span class="interest-card-label">{{ interest.label }}</span></div></div></div></div></section>
    <section class="section goals-section" aria-labelledby="goals-heading"><div class="container"><p class="section-label">What's Next</p><h2 class="section-title" id="goals-heading">My Learning <em>Goals</em></h2><p class="section-subtitle">A structured look at where I've been, where I am, and where I'm heading in my web development journey.</p><div class="goals-table-wrap"><table><thead><tr><th>Goal / Topic</th><th>Category</th><th>Target Date</th><th>Status</th><th>Notes</th></tr></thead><tbody><tr v-for="goal in goals" :key="goal[0]"><td>{{ goal[0] }}</td><td>{{ goal[1] }}</td><td>{{ goal[2] }}</td><td><span class="badge" :class="goal[3] === 'Done' ? 'badge-done' : 'badge-progress'">{{ goal[3] }}</span></td><td>{{ goal[4] }}</td></tr></tbody></table></div></div></section>
  </div>
</template>
