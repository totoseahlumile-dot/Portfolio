<script setup>
import portrait from '../assets/images/IMG_2008.jpg';

const emit = defineEmits(['navigate']);
const highlights = [
  { title: 'Goal-Oriented', desc: 'I set clear goals and keep building toward them.' },
  { title: 'Always Learning', desc: 'Every project helps me sharpen my skills and thinking.' },
  { title: 'Team Player', desc: 'I enjoy collaborating and learning from others.' },
  { title: 'Creative Thinker', desc: 'I like solving problems with both logic and design.' },
];
const journey = [
  { date: 'March 2026', title: 'The Beginning: Hello, World!', desc: 'I wrote my first line of Python and discovered the spark that ignited my passion for coding.' },
  { date: 'March 2026', title: 'Discovering HTML & CSS', desc: 'I created my first webpage, then added colour, fonts, and spacing with CSS.' },
  { date: 'April 2026', title: 'Mastering CSS', desc: 'I learned the box model, positioning, and layouts to make pages more polished.' },
  { date: 'May 2026', title: 'Animated Product Showcase', desc: 'I built a product showcase with animated effects and responsive cards.' },
  { date: 'Now', title: 'Building This Portfolio', desc: 'I am bringing everything together into a complete personal portfolio website.' },
];
</script>

<template>
  <div class="page-view" style="display: contents">
    <section class="page-hero"><div class="container"><p class="section-label">Get to Know Me</p><h1 class="section-title">About <em>Me</em></h1><p class="section-subtitle">My story, my interests, and the path that brought me to web development.</p></div></section>
    <section class="section"><div class="container"><div class="about-grid"><div class="about-img-col"><div class="about-card"><div class="about-card-img"><img :src="portrait" alt="Ahlumile Totose" class="about-profile-img" /></div><div class="about-card-body"><h2 class="about-card-name">Ahlumile Totose</h2><p class="about-card-role">Web Developer &amp; Student</p><div class="about-card-info"><div class="info-row">Cape Town, South Africa</div><div class="info-row">Life Choices Academy / YouthCode</div><div class="info-row">Started coding in March 2026</div><div class="info-row">Full Stack Developer in Training</div></div></div></div></div><div class="about-text"><p class="section-label">My Story</p><h2 class="section-title">Who <em>I Am</em></h2><p>Hi there! I'm <strong>Ahlumile Totose</strong>, a passionate and curious learner studying at <strong>LifeChoices Academy / YouthCode</strong>.</p><p>What began as a beginner coding journey quickly became a genuine passion. I enjoy learning how things work behind the scenes and turning ideas into interactive digital experiences.</p><p>I come from a background in <strong>Science</strong>, and I believe that curiosity, creativity, and persistence are powerful tools in tech.</p><div class="about-highlights"><div v-for="highlight in highlights" :key="highlight.title" class="highlight-item"><div class="highlight-title">{{ highlight.title }}</div><div class="highlight-desc">{{ highlight.desc }}</div></div></div></div></div></div></section>
    <section class="section journey-section"><div class="container"><p class="section-label">My Path</p><h2 class="section-title">My Learning <em>Journey</em></h2><div class="timeline"><article v-for="item in journey" :key="item.title" class="timeline-item"><div class="timeline-dot" aria-hidden="true">*</div><div class="timeline-content"><p class="timeline-date">{{ item.date }}</p><h3 class="timeline-title">{{ item.title }}</h3><p class="timeline-desc">{{ item.desc }}</p></div></article></div></div></section>
    <section class="section" style="background: var(--clr-secondary); color: #fff;"><div class="container" style="max-width:760px; text-align:center;"><p class="section-label" style="color:var(--clr-accent);">Looking Back</p><h2 class="section-title" style="color:#fff;">My <em style="color:var(--clr-accent)">Reflection</em></h2><blockquote style="font-family:var(--ff-display); font-size:1.5rem; font-style:italic; line-height:1.5; color:rgba(255,255,255,.85); margin:2rem 0; padding:2rem; border-left:4px solid var(--clr-accent); text-align:left; border-radius:0 12px 12px 0; background:rgba(255,255,255,.05);">&quot;Learning to code has been one of the most challenging and rewarding experiences of my life. Every error message taught me something new, and every working page felt like a small victory.&quot;</blockquote><p style="color:rgba(255,255,255,.7); margin-bottom:2.5rem;">This journey has taught me patience, persistence, and the importance of breaking big problems into small pieces.</p><a href="#projects" class="btn btn-primary" @click.prevent="emit('navigate', 'projects')">See What I've Built</a></div></section>
  </div>
</template>
