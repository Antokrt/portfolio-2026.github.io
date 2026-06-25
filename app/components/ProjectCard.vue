<template>
  <article class="project-card" :class="{ 'is-featured': featured }">

    <!-- Image -->
    <div class="card-img-wrap">
      <NuxtImg
        :src="`https://picsum.photos/seed/${slug}/800/600`"
        :alt="title"
        loading="lazy"
        width="800"
        height="600"
      />
    </div>

    <!-- Gradient overlay -->
    <div class="card-overlay" />

    <!-- Category pill -->
    <span class="card-category">{{ category }}</span>

    <!-- Bottom content -->
    <div class="card-content">
      <h3 class="card-title">{{ title }}</h3>
      <p class="card-desc">{{ description }}</p>
      <span class="card-cta">Voir le projet →</span>
    </div>

  </article>
</template>

<script setup>
defineProps({
  title:       { type: String, required: true },
  category:    { type: String, required: true },
  slug:        { type: String, required: true },
  description: { type: String, default: '' },
  featured:    { type: Boolean, default: false }
})
</script>

<style scoped>
.project-card {
  position: relative;
  border-radius: 22px;
  overflow: hidden;
  width: 100%;
  height: 100%;
  cursor: pointer;
}

/* Image */
.card-img-wrap {
  position: absolute;
  inset: 0;
}

.card-img-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.60s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  will-change: transform;
}

.project-card:hover .card-img-wrap img {
  transform: scale(1.07);
}

/* Gradient overlay */
.card-overlay {
  position: absolute;
  inset: 0;
  z-index: 1;
  background: linear-gradient(
    to bottom,
    rgba(4, 16, 30, 0.02) 0%,
    rgba(4, 16, 30, 0.10) 45%,
    rgba(4, 16, 30, 0.72) 100%
  );
  transition: background 0.40s ease;
}

.project-card:hover .card-overlay {
  background: linear-gradient(
    to bottom,
    rgba(4, 16, 30, 0.08) 0%,
    rgba(4, 16, 30, 0.22) 40%,
    rgba(4, 16, 30, 0.88) 100%
  );
}

/* Category pill — top left */
.card-category {
  position: absolute;
  top: 16px;
  left: 16px;
  z-index: 2;
  font-family: 'Inter', sans-serif;
  font-size: 9px;
  font-weight: 500;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.80);
  background: rgba(255, 255, 255, 0.14);
  backdrop-filter: blur(14px) saturate(180%);
  -webkit-backdrop-filter: blur(14px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.28);
  border-radius: 999px;
  padding: 5px 12px;
}

/* Bottom content */
.card-content {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 2;
  padding: 20px 18px 18px;
}

.card-title {
  font-family: 'Inter', sans-serif;
  font-size: 15px;
  font-weight: 600;
  color: #ffffff;
  margin: 0 0 5px 0;
  line-height: 1.25;
  letter-spacing: -0.01em;
}

.is-featured .card-title {
  font-size: 20px;
  margin-bottom: 6px;
}

.card-desc {
  font-family: 'Inter', sans-serif;
  font-size: 11px;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.52);
  margin: 0;
  opacity: 0;
  transform: translateY(6px);
  transition: opacity 0.30s ease 0.05s, transform 0.35s ease 0.05s, margin-bottom 0.30s ease 0.05s;
}

.project-card:hover .card-desc {
  opacity: 1;
  transform: translateY(0);
  margin-bottom: 12px;
}

.card-cta {
  display: inline-block;
  font-family: 'Inter', sans-serif;
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 0.10em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.50);
  opacity: 0;
  transform: translateY(5px);
  transition: opacity 0.30s ease 0.08s, transform 0.35s ease 0.08s;
}

.project-card:hover .card-cta {
  opacity: 1;
  transform: translateY(0);
}
</style>
