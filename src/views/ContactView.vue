<script setup>
import { ref } from 'vue';

const formSubmitted = ref(false);
const achievements = [
  ['Built 8+ Projects', 'Created multiple responsive web projects, including landing pages, portfolio work, and interactive showcases.'],
  ['Learned Core Web Skills', 'Strengthened my foundation in HTML, CSS, JavaScript, Vue, PHP, and Python through consistent practice.'],
  ['Responsive Design', 'Designed pages that adapt smoothly across desktop, tablet, and mobile screen sizes.'],
  ['GitHub Workflow', 'Used Git and GitHub to manage versions, track progress, and publish work effectively.'],
  ['Portfolio Launch', 'Completed a personal portfolio that brings together my skills, projects, and growth as a developer.'],
];

function submitForm() {
  formSubmitted.value = true;
}
</script>

<template>
  <div class="page-view" style="display: contents">
    <section class="page-hero"><div class="container"><p class="section-label">Let's Connect</p><h1 class="section-title">Get In <em>Touch</em></h1><p class="section-subtitle">Whether you want to collaborate, give feedback, or just say hello, I'd love to hear from you.</p></div></section>
    <section class="section"><div class="container"><div class="contact-grid"><div class="contact-info"><h2>Say <em style="font-style:italic; color:var(--clr-primary)">Hello!</em></h2><p>I'm always happy to connect with fellow learners, potential collaborators, or anyone interested in web development.</p><div class="contact-methods"><div class="contact-method"><div class="contact-method-icon">@</div><div><div class="contact-method-label">Email</div><div class="contact-method-value">totoseahlumile@email.com</div></div></div><div class="contact-method"><div class="contact-method-icon">GH</div><div><div class="contact-method-label">GitHub</div><div class="contact-method-value">totoseahlumile-dot</div></div></div><div class="contact-method"><div class="contact-method-icon">SA</div><div><div class="contact-method-label">Location</div><div class="contact-method-value">Cape Town, South Africa</div></div></div></div></div><div class="contact-form"><h3>Send Me a Message</h3><form @submit.prevent="submitForm"><div class="form-row"><div class="form-group"><label for="firstName">First Name <span>*</span></label><input id="firstName" required placeholder="e.g. Jane" /></div><div class="form-group"><label for="lastName">Last Name <span>*</span></label><input id="lastName" required placeholder="e.g. Smith" /></div></div><div class="form-group"><label for="email">Email Address <span>*</span></label><input id="email" type="email" required placeholder="jane@example.com" /></div><div class="form-group"><label for="subject">Subject <span>*</span></label><select id="subject" required><option value="" disabled>Select a topic...</option><option>Feedback</option><option>Collaboration</option><option>Opportunity</option><option>Question</option></select></div><div class="form-group"><label for="message">Message <span>*</span></label><textarea id="message" required minlength="20" placeholder="Tell me what's on your mind..."></textarea></div><button type="submit" class="btn btn-primary form-submit">Send Message</button><p v-if="formSubmitted" role="status" style="margin-top:1rem; color:var(--clr-secondary)">Thanks, your message is ready to send.</p></form></div></div></div></section>
    <section class="section" style="background:var(--clr-secondary); color:#fff;"><div class="container"><p class="section-label" style="color:var(--clr-accent);">Milestones</p><h2 class="section-title" style="color:#fff;">My <em style="color:var(--clr-accent)">Achievements</em></h2><p class="section-subtitle" style="color:rgba(255,255,255,.65);">Small wins on the journey to becoming a developer.</p><div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:1.5rem;"><div v-for="achievement in achievements" :key="achievement[0]" class="skill-category"><h3 class="skill-cat-title">{{ achievement[0] }}</h3><p style="font-size:.88rem; color:rgba(255,255,255,.65);">{{ achievement[1] }}</p></div></div></div></section>
  </div>
</template>
