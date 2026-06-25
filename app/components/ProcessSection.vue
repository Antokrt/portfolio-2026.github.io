<template>
  <section class="process" id="process">

    <div class="blob blob-1" />
    <div class="blob blob-2" />
    <div class="blob blob-3" />

    <div class="card">

      <div class="card-header">
        <div class="header-line" />
        <h2 class="card-title">Votre site en 4 étapes</h2>
        <p class="card-sub">Un processus clair, sans jargon et sans mauvaise surprise —<br />vous savez exactement où on en est à chaque moment.</p>
      </div>

      <div class="stepper">
        <div v-for="(step, i) in steps" :key="i" class="step" :class="{ 'is-last': i === steps.length - 1 }">

          <!-- Cercle numéroté + track -->
          <div class="step-top">
            <div class="step-num">{{ String(i + 1).padStart(2, '0') }}</div>
          </div>

          <!-- Contenu -->
          <div class="step-body">
            <div class="step-icon">{{ step.icon }}</div>
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-desc">{{ step.desc }}</p>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const steps = [
  {
    icon: '💬',
    title: 'On se rencontre',
    desc: 'Échange de 30 min pour cerner votre activité, vos objectifs et votre vision.'
  },
  {
    icon: '📋',
    title: 'On cadre le projet',
    desc: 'Contenu, délais et budget définis ensemble. Rien ne commence sans votre accord.'
  },
  {
    icon: '🎨',
    title: 'Je design & développe',
    desc: 'Site sur-mesure, rapide et optimisé pour le référencement Google.'
  },
  {
    icon: '🚀',
    title: 'Votre site est lancé',
    desc: 'Mise en ligne, tests complets, formation et fichiers sources livrés.'
  },
]
</script>

<style scoped>
/* ── Section ── */
.process {
  background: #ffffff;
  padding: 64px 32px 72px;
  position: relative;
}

/* ── Blobs ── */
.blob {
  position: absolute;
  pointer-events: none;
}

.blob-1 {
  width: 220px; height: 200px;
  top: 30px; left: 30px;
  background: rgba(74, 144, 226, 0.18);
  border-radius: 62% 38% 30% 70% / 58% 32% 68% 42%;
  animation: blobA 10s ease-in-out infinite;
}

.blob-2 {
  width: 200px; height: 180px;
  bottom: 30px; right: 30px;
  background: rgba(74, 144, 226, 0.14);
  border-radius: 32% 68% 54% 46% / 48% 62% 38% 52%;
  animation: blobB 13s ease-in-out infinite;
}

.blob-3 {
  width: 160px; height: 150px;
  top: 50%; left: 50%;
  transform: translate(-160%, -50%);
  background: rgba(74, 144, 226, 0.11);
  border-radius: 50% 50% 30% 70% / 40% 60% 40% 60%;
  animation: blobC 8s ease-in-out infinite;
}

@keyframes blobA {
  0%, 100% { transform: translateY(0)     scale(1);    border-radius: 62% 38% 30% 70% / 58% 32% 68% 42%; }
  50%       { transform: translateY(-14px) scale(1.05); border-radius: 42% 58% 55% 45% / 48% 52% 48% 52%; }
}
@keyframes blobB {
  0%, 100% { transform: translateY(0)    scale(1);    border-radius: 32% 68% 54% 46% / 48% 62% 38% 52%; }
  50%       { transform: translateY(12px) scale(1.04); border-radius: 52% 48% 38% 62% / 58% 42% 58% 42%; }
}
@keyframes blobC {
  0%, 100% { transform: translate(-160%, -50%) scale(1);    border-radius: 50% 50% 30% 70% / 40% 60% 40% 60%; }
  50%       { transform: translate(-160%, -50%) scale(1.06); border-radius: 35% 65% 55% 45% / 60% 40% 60% 40%; }
}

/* ── Carte ── */
.card {
  position: relative;
  z-index: 1;
  background: #ffffff;
  border-radius: 20px;
  box-shadow: 0 4px 40px rgba(0, 0, 0, 0.07);
  max-width: 960px;
  margin: 0 auto;
  padding: 52px 48px 56px;
}

/* ── En-tête ── */
.card-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 56px;
}

.header-line {
  width: 30px; height: 3px;
  background: #4A90E2;
  border-radius: 2px;
  margin-bottom: 16px;
}

.card-title {
  font-family: 'Inter', sans-serif;
  font-size: 28px;
  font-weight: 700;
  color: #111;
  margin: 0 0 10px;
  text-align: center;
}

.card-sub {
  font-family: 'Inter', sans-serif;
  font-size: 14px;
  color: #999;
  text-align: center;
  line-height: 1.7;
  margin: 0;
}

/* ── Stepper ── */
.stepper {
  display: flex;
  gap: 0;
}

.step {
  flex: 1;
  min-width: 0;
  position: relative;
  padding-right: 48px;
}

.step.is-last {
  padding-right: 0;
}

/* ── Cercle + track ── */
.step-top {
  position: relative;
  margin-bottom: 28px;
}

/* Track horizontal vers l'étape suivante */
.step:not(.is-last) .step-top::after {
  content: '';
  position: absolute;
  left: 52px;
  right: -48px;
  top: 22px;
  height: 2px;
  background: linear-gradient(to right, rgba(74, 144, 226, 0.45), rgba(74, 144, 226, 0.08));
  border-radius: 1px;
}

.step-num {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: linear-gradient(135deg, #4A90E2 0%, #2d6bbf 100%);
  color: #ffffff;
  font-family: 'Inter', sans-serif;
  font-size: 14px;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 14px rgba(74, 144, 226, 0.38);
  position: relative;
  z-index: 1;
  letter-spacing: 0.02em;
}

/* ── Contenu ── */
.step-body {
  padding-right: 12px;
}

.step-icon {
  font-size: 22px;
  width: 42px;
  height: 42px;
  background: #f0f5ff;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 16px;
}

.step-title {
  font-family: 'Inter', sans-serif;
  font-size: 15px;
  font-weight: 600;
  color: #111;
  margin: 0 0 10px;
  line-height: 1.3;
}

.step-desc {
  font-family: 'Inter', sans-serif;
  font-size: 13px;
  color: #888;
  line-height: 1.65;
  margin: 0;
}

/* ── Mobile ── */
@media (max-width: 700px) {
  .process { padding: 40px 16px 48px; }
  .blob { display: none; }

  .card { padding: 28px 20px 36px; border-radius: 14px; }
  .card-title { font-size: 22px; }
  .card-sub br { display: none; }
  .card-header { margin-bottom: 32px; }

  /* Vertical stepper */
  .stepper { flex-direction: column; gap: 0; }

  .step {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    gap: 16px;
    padding-right: 0;
    padding-bottom: 28px;
    position: relative;
  }

  .step.is-last { padding-bottom: 0; }

  /* Track vertical */
  .step-top { margin-bottom: 0; flex-shrink: 0; }

  .step:not(.is-last) .step-top::after {
    left: 21px;
    right: auto;
    top: 44px;
    bottom: -28px;
    width: 2px;
    height: auto;
    background: linear-gradient(to bottom, rgba(74,144,226,0.45), rgba(74,144,226,0.08));
  }

  .step-body { padding-right: 0; padding-top: 8px; }
  .step-num { width: 42px; height: 42px; font-size: 13px; }
}
</style>
