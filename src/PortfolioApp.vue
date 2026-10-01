<script setup>
import { computed, onBeforeUnmount, onMounted, ref } from 'vue';
import AboutView from './views/AboutView.vue';
import ContactView from './views/ContactView.vue';
import HomeView from './views/HomeView.vue';
import ProjectsView from './views/ProjectsView.vue';
import SiteFooter from './components/SiteFooter.vue';
import SiteNavigation from './components/SiteNavigation.vue';

const views = {
  home: HomeView,
  about: AboutView,
  projects: ProjectsView,
  contact: ContactView,
};

const page = ref(window.location.hash.slice(1) || 'home');
const showBackTop = ref(false);
const currentPage = computed(() => views[page.value] ? page.value : 'home');
const currentView = computed(() => views[currentPage.value]);

function navigate(nextPage) {
  page.value = views[nextPage] ? nextPage : 'home';
  window.location.hash = page.value;
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function handleHashChange() {
  page.value = window.location.hash.slice(1) || 'home';
}

function updateBackTopVisibility() {
  showBackTop.value = window.scrollY > 400;
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

onMounted(() => {
  window.addEventListener('hashchange', handleHashChange);
  window.addEventListener('scroll', updateBackTopVisibility);
});

onBeforeUnmount(() => {
  window.removeEventListener('hashchange', handleHashChange);
  window.removeEventListener('scroll', updateBackTopVisibility);
});
</script>

<template>
  <div id="portfolio-app">
    <SiteNavigation :current-page="currentPage" @navigate="navigate" />
    <main>
      <component :is="currentView" @navigate="navigate" />
    </main>
    <SiteFooter @navigate="navigate" />
    <button class="back-top" :class="{ visible: showBackTop }" aria-label="Back to top" @click="scrollToTop">↑</button>
  </div>
</template>