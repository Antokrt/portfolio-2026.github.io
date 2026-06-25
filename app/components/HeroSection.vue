<template>
  <section class="hero">

    <div class="hero-badge">
      <span>✦ Disponible pour de nouveaux projets</span>
    </div>

    <h1 class="hero-title">
      <span class="line-greeting">Votre meilleure vitrine,</span>
      <em class="line-main">c'est votre site.</em>
    </h1>



  </section>
</template>

<style scoped>
.hero {
  position: relative;
  z-index: 1;
  padding: 60px 32px 360px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 28px;
}

.hero::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 220px;
  background: linear-gradient(to bottom, transparent, #ffffff);
  pointer-events: none;
  z-index: 0;
}

/* Badge */
.hero-badge {
  display: inline-flex;
  align-items: center;
  background: rgba(255, 255, 255, 0.18);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.45);
  border-radius: 999px;
  padding: 6px 18px;
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.5);
  animation: fadeUp 0.6s ease both;
}

.hero-badge span {
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.92);
  letter-spacing: 0.02em;
}

/* Titre */
.hero-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  display: flex;
  flex-direction: column;
  gap: 2px;
  animation: fadeUp 0.65s ease 0.1s both;
}

.line-greeting {
  display: block;
  font-size: clamp(24px, 3.8vw, 48px);
  font-weight: 400;
  color: rgba(255, 255, 255, 0.82);
  text-shadow: 0 2px 20px rgba(8, 28, 50, 0.2);
}

.line-main {
  display: block;
  font-size: clamp(40px, 7.5vw, 92px);
  font-weight: 700;
  font-style: italic;
  color: #ffffff;
  line-height: 1.0;
  letter-spacing: -0.025em;
  text-shadow: 0 4px 32px rgba(8, 28, 50, 0.25);
}



@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

@media (max-width: 640px) {
  .hero { padding: 52px 24px 280px; gap: 18px; }
  .hero::after { height: 180px; }
  .hero-badge span { font-size: 11px; }
}
</style>
