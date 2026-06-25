<template>
  <div class="page">

    <AppHeader />

    <!-- Hero sur fond bleu ciel -->
    <HeroSection />

    <!-- Carte blanche émergente -->
    <div class="content-card">
      <MarqueeBand />

      <section id="portfolio" class="portfolio-section">
        <ProjectsRow />
      </section>

      <AboutSection />

      <ProcessSection />
    </div>

  </div>
</template>

<script setup>
useHead({
  title: 'Antonin Koreta — Développeur Sites Vitrines',
  meta: [
    {
      name: 'description',
      content: 'Développeur freelance spécialisé en sites vitrines modernes et performants pour artisans, restaurateurs et professionnels de santé.'
    },
    { property: 'og:title', content: 'Antonin Koreta — Développeur Sites Vitrines' },
    {
      property: 'og:description',
      content: 'Sites vitrines sur-mesure qui captivent et convertissent vos visiteurs en clients fidèles.'
    },
    { property: 'og:image', content: 'https://picsum.photos/seed/og-portfolio/1200/630' },
    { name: 'robots', content: 'index, follow' }
  ]
})
</script>

<style scoped>
.page {
  position: relative;
  z-index: 1;
  min-height: 100vh;
}

/* Carte blanche qui émerge du ciel bleu */
.content-card {
  position: relative;
  z-index: 2;
  background: #ffffff;
  border-radius: 52px 52px 0 0;
  margin-top: -2px;
  padding-bottom: 40px;
  box-shadow: 0 -2px 40px rgba(10, 34, 56, 0.07);
}

/* Section projets */
.portfolio-section {
  padding: 64px 48px 32px;
}


@media (max-width: 768px) {
  .content-card {
    border-radius: 28px 28px 0 0;
    margin-top: -48px;
    padding-bottom: 60px;
  }
  .portfolio-section { padding: 32px 16px 16px; }
}

@media (max-width: 480px) {
  .content-card { border-radius: 20px 20px 0 0; margin-top: -32px; }
}
</style>
