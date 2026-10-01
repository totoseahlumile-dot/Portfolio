<script setup>
defineProps({
  project: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <article class="project-card">
    <div
      class="project-card-header"
      :class="{ 'project-card-header--has-hover-image': project.hoverImage }"
      :style="{ background: project.color }"
    >
      <img :src="project.image" :alt="`${project.title} preview`" class="project-card-image" />
      <img
        v-if="project.hoverImage"
        :src="project.hoverImage"
        :alt="`${project.title} alternate preview`"
        class="project-card-image project-card-image--alternate"
      />
    </div>
    <div class="project-card-body">
      <div class="project-tags">
        <span v-for="tag in project.tags" :key="tag" class="project-tag">{{ tag }}</span>
      </div>
      <h3 class="project-title">{{ project.title }}</h3>
      <p class="project-desc">{{ project.description }}</p>
      <ul class="project-points">
        <li v-for="point in project.points" :key="point">{{ point }}</li>
      </ul>
      <div class="project-links" v-if="project.github || project.demo">
        <a v-if="project.github" :href="project.github" target="_blank" rel="noreferrer" class="btn btn-outline btn-small">GitHub</a>
        <a v-if="project.demo" :href="project.demo" target="_blank" rel="noreferrer" class="btn btn-primary btn-small">Live Demo</a>
      </div>
    </div>
  </article>
</template>
