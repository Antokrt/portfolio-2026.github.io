<template>
  <div class="mosaic">
    <div
      v-for="(project, index) in projects"
      :key="project.id"
      class="mosaic-item"
      :class="`item-${index + 1}`"
    >
      <ProjectCard
        :title="project.title"
        :category="project.category"
        :slug="project.slug"
        :description="project.description"
        :featured="index === 2"
      />
    </div>
  </div>
</template>

<script setup>
import { projects } from '~/data/projects.js'
</script>

<style scoped>
.mosaic {
  display: grid;
  grid-template-columns: 1.28fr 1fr 1fr;
  grid-template-rows: 278px 218px;
  gap: 14px;
}

/*
  [ item-3 FEATURED tall ] [ item-1 ] [ item-2 ]
  [ item-3 FEATURED tall ] [ item-4 ] [ item-5 ]
*/
.item-1 { grid-column: 2; grid-row: 1; }
.item-2 { grid-column: 3; grid-row: 1; }
.item-3 { grid-column: 1; grid-row: 1 / span 2; }
.item-4 { grid-column: 2; grid-row: 2; }
.item-5 { grid-column: 3; grid-row: 2; }

@media (max-width: 820px) {
  .mosaic {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 200px 180px 180px;
    gap: 10px;
  }

  .item-1 { grid-column: 1; grid-row: 1; }
  .item-2 { grid-column: 2; grid-row: 1; }
  .item-3 { grid-column: 1 / span 2; grid-row: 2; }
  .item-4 { grid-column: 1; grid-row: 3; }
  .item-5 { grid-column: 2; grid-row: 3; }
}

@media (max-width: 480px) {
  .mosaic {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(5, 200px);
    gap: 10px;
  }

  .item-1, .item-2, .item-3, .item-4, .item-5 {
    grid-column: 1;
    grid-row: auto;
  }
}
</style>
