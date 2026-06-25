<template>
  <section class="about" id="about">
    <div class="blob blob-1" />
    <div class="blob blob-2" />
    <span class="badge">ABOUT ME</span>
    <p class="about-text">
      Depuis <strong>3 ans</strong>, je crée des sites vitrines modernes
      qui convertissent vos visiteurs en clients fidèles.
    </p>
    <p class="about-sub">
      Chaque projet est pensé pour refléter votre identité,<br />
      attirer votre clientèle cible et vous démarquer de la concurrence.
    </p>
  </section>
</template>

<style scoped>
.about {
  position: relative;
  padding: 72px 40px 32px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 24px;
}

.blob {
  position: absolute;
  pointer-events: none;
  z-index: 0;
}

.blob-1 {
  width: 200px;
  height: 185px;
  top: 20px;
  right: 40px;
  background: rgba(74, 144, 226, 0.09);
  border-radius: 40% 60% 70% 30% / 50% 40% 60% 50%;
  animation: blobFloat1 9s ease-in-out infinite;
}

.blob-2 {
  width: 180px;
  height: 165px;
  bottom: 20px;
  left: 40px;
  background: rgba(74, 144, 226, 0.07);
  border-radius: 60% 40% 30% 70% / 40% 60% 40% 60%;
  animation: blobFloat2 11s ease-in-out infinite;
}

@keyframes blobFloat1 {
  0%, 100% { transform: translateY(0)    scale(1);    border-radius: 40% 60% 70% 30% / 50% 40% 60% 50%; }
  50%       { transform: translateY(-12px) scale(1.04); border-radius: 60% 40% 50% 50% / 40% 60% 40% 60%; }
}

@keyframes blobFloat2 {
  0%, 100% { transform: translateY(0)   scale(1);    border-radius: 60% 40% 30% 70% / 40% 60% 40% 60%; }
  50%       { transform: translateY(10px) scale(1.03); border-radius: 40% 60% 50% 50% / 60% 40% 60% 40%; }
}

.blob-3 {
  width: 140px;
  height: 130px;
  top: 35%;
  left: 18%;
  background: rgba(74, 144, 226, 0.05);
  border-radius: 50% 50% 40% 60% / 60% 40% 60% 40%;
}

.badge, .about-text, .about-sub {
  position: relative;
  z-index: 1;
}

.badge {
  display: inline-block;
  background: #e8f6fd;
  color: #1b3d56;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.14em;
  padding: 6px 18px;
  border-radius: 999px;
  border: 1px solid rgba(27, 61, 86, 0.15);
}

.about-text {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  font-size: clamp(22px, 3.5vw, 36px);
  font-weight: 400;
  color: #0a2233;
  line-height: 1.5;
  max-width: 640px;
}

.about-text strong {
  font-weight: 700;
}

.about-sub {
  font-size: 15px;
  color: #5a7a90;
  line-height: 1.7;
  max-width: 480px;
  font-weight: 400;
}

@media (max-width: 600px) {
  .about { padding: 52px 20px 48px; gap: 16px; }
  .blob { display: none; }
  .about-sub br { display: none; }
}
</style>
